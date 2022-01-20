# GCM-Filters: A Python Package for Spatial Filtering of Gridded Data from Ocean and Climate Models

### 12th Symposium on Advances in Modeling and Analysis Using Python

#### January 25, 2022

#### Contributors:

[Nora Loose](https://noraloose.github.io/)

[Ryan Abernathey](https://github.com/rabernat), [Ian Grooms](https://github.com/iangrooms), [Julius Busecke](http://jbusecke.github.io/), [Arthur Barthe](https://github.com/arthurBarthe), [Elizabeth Yankovsky](https://github.com/ElizabethYankovsky), [Gustavo Marques](https://github.com/gustavo-marques), [Jacob Steinberg](https://github.com/jakesteinberg), [Andrew Slavin Ross](https://github.com/asross), [Hemant Khatri](https://github.com/hmkhatri), [Scott Bachman](https://github.com/sdbachman), [Laure Zanna](https://github.com/LaureZanna), and [Paige Martin](https://github.com/paigem)

#### Abstract:

Applying a spatial filter to gridded data from models or observations is a common analysis method in the Earth Sciences, for example to study oceanic and atmospheric motions at different spatial scales or to develop subgrid-scale parameterizations for ocean models. The spatial filters that are included in existing python packages, such as SciPy's multidimensional Gaussian filter, are typically specialized for image processing. For data from General Circulation Models (GCMs), image processing tools are however of limited use because these tools assume a regular and rectangular Cartesian grid and employ simple boundary conditions. In contrast, GCMs come on irregular curvilinear grids, and continental boundaries in GCMs need more careful treatment than currently supported. 

Here we introduce a new python package, GCM-Filters, which is specifically designed to filter GCM data. The GCM-Filters algorithm applies a discrete Laplacian to smooth a field through an iterative process that resembles diffusion. The discrete Laplacian takes into account the varying grid-cell geometry of the complex GCM grids and uses a no-flux boundary condition, mimicking how diffusion is internally implemented in GCMs and ensuring conservation of the integral. Conservation of the integral is a desirable filter property for many physical quantities, for example energy or ocean salinity. The user can employ GCM-Filters on either CPUs or GPUs, with NumPy or CuPy input data. Moreover, GCM-Filters leverages Dask and Xarray to support filtering of larger-than-memory datasets and computational flexibility.

In this talk, we will present examples of how to use GCM-Filters in a range of oceanographic applications. Ongoing development of the GCM-Filters package is hosted on GitHub at https://github.com/ocean-eddy-cpt/gcm-filters, with community contributions welcome.

### Access the presentation slides

We used [`reveal.js`](https://github.com/hakimel/reveal.js) to create this presentation.

To build the html file, run these lines at the terminal within the repository:
```bash
jupyter nbconvert index.ipynb --to slides --reveal-prefix reveal.js --SlidesExporter.reveal_transition=none --SlidesExporter.reveal_scroll=True

mv index.slides.html index.html # renames the html file
```
