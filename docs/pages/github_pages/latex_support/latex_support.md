---
Title: LaTeX support
nav_order: 4
parent: GitHub Pages
---

# LaTeX Support

[LaTeX](http://www.latex-project.org/) is an great tool, especially useful for the typesetting of complex mathematical formulas. [Mathjax](http://docs.mathjax.org/en/latest/basic/mathjax.html) allows page authors to write formulas using LaTeX notation.

## Use MathJax for Jekyll

To implement Mathjax, you need to [customize your theme's html layout](https://help.github.com/en/github/working-with-github-pages/adding-a-theme-to-your-github-pages-site-using-jekyll). To do so:

* On GitHub, navigate to your theme's source repository. At the Campbell Muscle Lab, we use [just-the-docs](https://pmarsceill.github.io/just-the-docs/).

* In the \_layouts folder, navigate to your theme's default.html file.

* Copy the contents of the file.

* On GitHub, navigate to your site's repository, where the \_config.yml file is located.

* Create a file called \_layouts/default.html.

* Paste the default layout content you copied earlier.

* Customize the layout by adding this code:

````
<script type="text/x-mathjax-config"> MathJax.Hub.Config({ TeX: { equationNumbers: { autoNumber: "none" } } }); </script> 

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  tex2jax: {
	inlineMath: [['$','$'], ['\\(','\\)']],
	displayMath: [ ['$$', '$$'] ],
	processEscapes: true,
	processEnvironments: true
	}
}); 
```` 
## An example

You can now insert LaTeX-like equations in your Markdown files. For instance, the following code:

````
There are two solutions to the quadratic equation $a x^2 + b x + c = 0$:

$$ x_{1,2} = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$
````

will produce:

![Latex equation](equations.png)

## Tips

Some [difficulties](http://docs.mathjax.org/en/latest/input/tex/html.html#interactions-with-content-management-systems) may arise when MathJax is used in content-management systems (like Markdown) that have their own document processing commands that are interpreted before the HTML page is created. For instance, the hash symbol \# is interpreted by Markdown before LaTeX and thus can lead to a bad rendering of the equations. Here are a few tips to overcome some of these difficulties.

* \#
	
Use the \unicode{x23} command.
	
* \< or \>
	
Use the \lt or \gt command.
	
* Matrix 
	
Use \\\\\ instead of \\\ to create a new line in the matrix.






