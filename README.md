SimpleSidebar
===============
2019-06-10


A simple sidebar widget written in jquery.





Demo: https://lingtalfi.com/simplesidebar





<h2>The html architecture</h2>
<p>
    First, we need to create the html structure.
    The html structure is composed of a wrapper (called context) containing all
    elements
    pertaining to the sidebar widget.
</p>
<p>
    Those elements are:
</p>
<ul>
    <li>a header (<code>.page-header</code>) containing the sidebar toggler (which toggles the sidebar
        on/off)
    </li>
    <li>a body (<code>.page-body</code>)</li>
    <li>a footer (<code>.page-footer</code>)</li>
</ul>

<p>
    The sidebar itself is contained in the body, which contains the following
    elements:
</p>
<ul>
    <li>the sidebar (<code>.widget-sidebar</code>)</li>
    <li>the main content (<code>.page-main</code>)</li>
</ul>



<h2>How does the sidebar behave?</h2>
<p>
    The sidebar has a default behaviour.<br>
    By default, the sidebar is responsive, and so it reacts to a break point
    automatically: it basically disappears on small screens, and re-appears on
    large screens.
    <br>
    However, once you've click on the <strong>sidebar toggler button</strong> (in the header),
    you switch to a <u class="text-nowrap">manual mode</u>, where the sidebar toggles only when you click
    that toggler button (i.e. it doesn't respond to break points anymore).
    <br>
    In short, you are in <u class="text-nowrap">automatic mode</u> until you click the toggler button,
    which then switches you to the manual mode until you refresh the page again.
</p>

<h2>The dynamic markup</h2>
<p>
    In this section we list the important html markup which makes the sidebar
    alive.

</p>
<h3 class="h6">The active state</h3>
<p>
    By default, all sidebar items have the same style.
    To emphasize that a sidebar item is active (selected), we add the <code>.active</code>
    class to it (to the <code>li</code> element).
</p>
<h3 class="h6">Parent/Children relationship</h3>
<p>
    The sidebar items are like leaves of a tree, some of them contain children,
    some other don't.<br>
    To create a parent, we need to add an <code>a</code> tag inside the <code>li</code> item,
    and this <code>a</code> tag contains another <code>ul</code> containing
    the children items.
</p>
<p>
On the <code>a</code> tag of the parent node, we need to add the following markup:
</p>
<ul>
    <li><b>href</b>: #<code>$target</code> (you choose <code>$target</code> arbitrarily)</li>
    <li><b>data-toggle</b>: collapse</li>
    <li><b>aria-expanded</b>: true|false (either true or false)</li>
    <li><b>class</b>: dropdown-toggle</li>
</ul>
<p>
    And then on the <code>ul</code> tag of the parent element, add the following:
</p>
<ul>
    <li><b>class</b>: collapse</li>
    <li><b>class</b>: show (if you want to display the children)</li>
    <li><b>id</b>: <code>$target</code></li>
</ul>


History Log
------------------
    
- 1.0.0 -- 2019-06-10

    - initial commit
    