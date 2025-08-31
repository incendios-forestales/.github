# Imagen de rocker/geospatial que se utiliza como base
FROM rocker/geospatial:4.5.1

ENV DEBIAN_FRONTEND=noninteractive

# Dependencia que exige keyring en Linux
RUN apt-get update && apt-get install -y --no-install-recommends \
    libsecret-1-0 \
&& rm -rf /var/lib/apt/lists/*

# Fijar CRAN en HTTPS y usar todos los cores por defecto
RUN bash -lc "echo \"options(repos = c(CRAN='https://cloud.r-project.org'), \
    Ncpus = max(1L, parallel::detectCores()-1L))\" \
    >> /usr/local/lib/R/etc/Rprofile.site"

# Exponer RStudio Server
EXPOSE 8787

# Instalar remotes una vez y luego las versiones fijadas
RUN R -q -e "install.packages('remotes'); \
  remotes::install_version('here',               version='1.0.1'); \
  remotes::install_version('kableExtra',         version='1.4.0'); \
  remotes::install_version('DT',                 version='0.33'); \
  remotes::install_version('ggthemes',           version='5.1.0'); \
  remotes::install_version('hrbrthemes',         version='0.8.7'); \
  remotes::install_version('plotly',             version='4.11.0'); \
  remotes::install_version('rnaturalearth',      version='1.1.0'); \
  remotes::install_version('rnaturalearthdata',  version='1.0.0'); \
  remotes::install_github('ropensci/rnaturalearthhires'); \
  remotes::install_github('ErikKusch/KrigR')"

