Embed syntax highlighted code blocks directly in your reST documents:



.. code:: Python



    from copy import deepcopy

    

    def resetDefaults(f):

        defaults = f.func_defaults

        def resetter(*args, **kwds):

            f.func_defaults = deepcopy(defaults)

            return f(*args, **kwds)

        resetter.__name__ = f.__name__

        return resetter



You can also embed an existing snippet:



.. snippet:: 1





Use :help:`math` like, :math:`E=mc^2` or : 



.. math:: align



     \nabla \cdot E &= \frac{1}{\epsilon_0} \rho\\

     \nabla \cdot B &= 0\\

     \nabla \times E &= -\frac{\partial B}{\partial t}\\

     \nabla \times B &= \mu_0 J + \mu_0 \epsilon_0 \frac{\partial E}{\partial t}





Or create flow graphs



.. graph::



    digraph finite_state_machine {

        rankdir=LR;

        size="2.5,2.5"

        node [shape = circle];

        

        A [fillcolor = cornflowerblue];

        B [fillcolor = red];

        C [fillcolor = gold];

        A -> C [ label = "A-C" color = cornflowerblue];

        A -> B [ label = "A-B" color = red];

        A -> A [ label = "WTF?"];

        C -> B;

        

    }



Another graph:



.. graph::



  node.hdr { color: red; }

  node.src { fill: lightgreen; }

  node.stage { fill: lightblue; }



  (Libraries: [Library 1]{ shape: diamond;},

              [Library 2]{ shape: diamond;},

              [Library 3]{ shape: diamond;})



  [Header 1]{class: hdr;},

  [Header 2]{class: hdr;},

  [Header N]{class: hdr;}-> [Preprocessor]{shape:circle; class:stage;} -> [Intermediate 2],

                                                                          [Intermediate 1] ->[Compiler]

  [Source 1]{class: src;}, [Source 2]{class: src;}-> [Preprocessor]



  [ Compiler ]{shape:circle; class:stage;} -> [ Object 2], [ Object 1] -> [ Linker ]



  [Library 1], [Library 2], [Library 3] -> [Linker]{shape:circle; class:stage;}

  [Linker] -> [Binary2]



Create :help:`charts`:



.. piechart::

  :title: Visitors with Firefox

  :data: 36.30, 55.40, 8.3

  :colors: f5f700, 0087f7, f79b00

  :labels: Firefox 3 (36.0%), Firefox 2.0.0.14 (55.40%), Other Firefox 2 (8.3%)

  :3d:





.. warning:: I am a warning. Be Warned!!!





Create tables



.. csv-table:: Frozen Delights!

   :header: "Treat", "Quantity", "Description"

   :widths: 15, 10, 30



   "Albatross", 2.99, "On a stick!"

   "Crunchy Frog", 1.49, "If we took the bones out, it wouldn't be

   crunchy, now would it?"

   "Gannet Ripple", 1.99, "On a stick!"





Another table



 ====================  ==========  ==========

 Header row, column 1  Header 2    Header 3

 ====================  ==========  ==========

 body row 1, column 1  column 2    column 3

 body row 2            Cells may span columns

 ====================  ======================



This is a paragraph.  It's quite

short.



   This paragraph will result in an indented block of

   text, typically used for quoting other text.



This is another one.



For *italics* surround the text with asterisk, like ``*italics*``.



For **bold** surround the text with double asterisk, like ``**bold**``



For inline literals, surround the text with double backticks (`), like ````literal````





Reference books like this:



.. book:: 0-321-33489-2



Where as the `:book:`0-321-33489-2``` interpreted text role, will create an inline title-based link referencing the 

:book:`0-321-33489-2` book.






