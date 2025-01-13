#  <img src="https://github.com/quantum-label/quantum_labelling_tool/blob/main/static/img/quantum_icon.png" width="50" style="vertical-align:middle"> QUANTUM - The Health Data Quality Label
  
![Python Version](https://img.shields.io/badge/python-3.11%2B-brightgreen.svg)
Cite the code: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.14637282.svg)](https://doi.org/10.5281/zenodo.14637282)

## Introduction

The **QUANTUM Data Quality Labelling Tool** is a key component of the **European Health Data Space (EHDS)** initiative, designed to address the challenge of ensuring that health datasets are of high quality, accessible, and interoperable across EU member states. As healthcare data plays an increasingly vital role in research, policy, and innovation, this tool provides a standardized mechanism to evaluate and label the **quality, utility, and maturity** of datasets, supporting stakeholders such as healthcare institutions, research organizations, and policymakers.

## Features

This tool empowers **data holders** by offering functionalities to:

- **Feature 1:** Catalogue and Dataset metadata creation
- **Feature 2:** Assess datasets quality based on a guided evaluation of the QUANTUM key dimensions (such as accuracy, accessibility, and compliance) using your own practices.
- **Feature 3:** Generate and visualise data quality certificates (labels) and download them in the HealthData@EU standardized RDF format.
- **Feature 4:** Facilitate compliance with EU-wide quality standards such as [HealthDCAT-AP](https://healthdcat-ap.github.io/), [DCAT](https://www.w3.org/TR/vocab-dcat-3/), [DQV](https://www.w3.org/TR/vocab-dqv/).
- **Feature 5:** Provide a transparent and accessible method for assessing data holders maturity.

Ultimately, the QUANTUM tool aims to foster **trust in health data** across Europe by promoting reliable, reusable datasets that can be confidently shared within the European Health Data Space.

## Requirements

Python 3.11


## Installation steps
```bash
git clone [repository_url]
cd [repository_directory]
pip install -r requirements.txt
python manage.py createsuperuser # for creating root user if desired (current root user is root for username and password)
python manage.py migrate # if database is not generated previously 
```

## Execution

```bash
python manage.py runserver 0.0.0.0:8000
```

- Access localhost:8000 through web browser
- Access localhost:8000/admin to visit the Admin dashboard (login is root for user and password by default)
- To register a user it is needed to 1) create the user, 2) create an organization, 3) relate a user with an organization (userorganization)

## Dockerizing

- Create a folder named "QUANTUM"
- Create a folder with all the files of the project "webapp"
- In the "webapp" folder put all the files but the docker folder as well as the .git folder
- In the "QUANTUM" folder copy the ".env", "docker-compose.yml", "Dockerfile", "quantum_init.sql" and "requirements.txt" files.
- In the "QUANTUM" folder execute by bash:
```bash
docker build -t quantum_online_tool .
```
- When the image is built execute the docker-compose command inside the "QUANTUM" folder:
```bash
docker-compose up
```
- Access the container through the following command:
```
docker exec -it quantumtoolwebapp bash
```
- See "Installation steps" and "Usage" sections

## Technology Stack

### Backend
- Python 3
- Django
### Frontend
- HTML
- CSS*
- JavaScript*

*It is used Bootstrap 5.3

### Database
#### Development
- SQLite3
#### Production (Docker)
- MariaDB

# Licence
This work is licensed under the Creative Commons Attribution-NonCommercial 4.0 International License. 
To view a copy of this license, visit [http://creativecommons.org/licenses/by-nc/4.0/](http://creativecommons.org/licenses/by-nc/4.0/).

![CC BY-NC 4.0](https://licensebuttons.net/l/by-nc/4.0/88x31.png)

## Credits
**Version:** 0.1

**Authors:** QUANTUM WP2: Claudio Proietti Mercuri (Sciensano), Ángel Sánchez-García (UPV), Nienke Schutte (Sciensano), Carlos Sáez (UPV); on behalf of [QUANTUM](https://quantumproject.eu).

**Maintainers:** Claudio Proietti Mercuri (Sciensano), Ángel Sánchez-García (UPV), Francisco Estupiñan Romero (IACS).

**Acknowledgements:** QUANTUM WP1, WP2, WP3 partners and all participants in the tool piloting for their feedback.

Funded by EU [QUANTUM](https://quantumproject.eu) project.
