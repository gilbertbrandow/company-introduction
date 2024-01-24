# Company Introduction
A dockerized Python CLI program that generates a report of a publically traded company based on ticker symbol.

# Prerequisites
1. [Install Docker](https://docs.docker.com/get-docker/)
2. Clone this repository

# Building the image and running the container

In order to use the application you will need to build an image and start a container of it.
1. You will first need to cd into the directory after cloning it `company-introduction`

```
cd company-introduction
```

2. Run the command below to build an image called `company_introduction_image` based on the `Dockerfile` that can be located in the root of the project

```
docker build -t company_introduction_image --rm .
```

3. Run the command below to start a container called `company-introduction` using the `company_introduction_image`

```
docker run --name company_introduction_container --rm -v /path/on/host:/usr/app/src/reports -it company_introduction_image
```
Replace /path/on/host with the absolute path on your host machine where you want to store the generated reports.

Note: If the path contains spaces, you may need to use quotes around the path, like this:

```
"/path/with spaces/on/host":"/usr/app/src/reports"
```

# Usage

In order to generate a report for the company run the below command while in the container

```
python main.py [TICKER SYMBOL]
```

**Example** 
Generating report for Netflix (Ticker symbol NFLX)

```
python main.py NFLX
```
