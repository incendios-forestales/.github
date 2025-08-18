# Imagen de rocker/geospatial que se utiliza como base
FROM rocker/geospatial:4.5.1

# Dependencia que exige keyring en Linux
RUN apt-get update && apt-get install -y --no-install-recommends \
    libsecret-1-0 \
 && rm -rf /var/lib/apt/lists/*

# Clave para ingresar a RStudio Server
ENV PASSWORD=incendios

# Puerto de RStudio Server
EXPOSE 8787

# Instalación del paquete here de R, versión 1.0.1
RUN R -e "devtools::install_version('here', version = '1.0.1', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete kableExtra de R, versión 1.4.0
RUN R -e "devtools::install_version('kableExtra', version = '1.4.0', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete DT de R, versión 0.33
RUN R -e "devtools::install_version('DT', version = '0.33', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete ggthemes de R, versión 5.1.0
RUN R -e "devtools::install_version('ggthemes', version = '5.1.0', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete hrbrthemes de R, versión 0.8.7
RUN R -e "devtools::install_version('hrbrthemes', version = '0.8.7', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete plotly de R, versión 4.11.0
RUN R -e "devtools::install_version('plotly', version = '4.11.0', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete rnaturalearth de R, versión 1.1.0
RUN R -e "devtools::install_version('rnaturalearth', version = '1.1.0', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete rnaturalearthdata de R, versión 1.0.0
RUN R -e "devtools::install_version('rnaturalearthdata', version = '1.0.0', repos = 'http://cran.us.r-project.org')"

# Instalación del paquete rnaturalearthhires de R (sin especificar la versión para elegir el más reciente)
RUN R -e "remotes::install_github('ropensci/rnaturalearthhires')"

# Instalación del paquete KrigR de R (sin especificar la versión para elegir el más reciente)
RUN R -e "remotes::install_github('ErikKusch/KrigR')"