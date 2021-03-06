# Jupyter-Docker

One of our use-cases involves the use of personal ephemeral (i.e. short-lived) compute environments.  As a result, the time and speed it takes to install Jupyter within that environment was a very important factor to us.  To address this we have developed a minimal [Jupyter Docker image (~340MB)](https://hub.docker.com/r/nbgallery/jupyter-alpine/) based on Alpine Linux.  This minimal image offers a dozen language kernels, most of which are installed dynamically when the user tries to open a new notebook in that language.  This avoids potentially ballooning the size of the image by trying to “bake in” each and every language kernel.

To maintain such a small image we also couldn’t include every possible language library that an analytic author might need.  Since many notebooks do require language libraries, we’ve created capabilities for both [Python](https://github.com/nbgallery/ipydeps) and [Ruby](https://github.com/nbgallery/iruby-dependencies) to allow language and OS dependencies to be installed on the fly when a user runs the notebook.  This means that users operating in these ephemeral environments do not have to know how to install packages from the command line in order to successfully execute the code within a nbgallery-hosted notebook.

Want to know more?  Read [this post]({{ site.baseurl }}{% link minimal_image.md %}) which goes into more detail.
