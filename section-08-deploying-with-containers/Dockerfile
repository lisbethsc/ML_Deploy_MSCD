FROM python:3.11

# Create the user that will run the app
RUN adduser --disabled-password --gecos '' ml-api-user

WORKDIR /opt

ARG PIP_EXTRA_INDEX_URL

RUN apt-get update
RUN apt-get install -y git

RUN git clone https://github.com/pablovillazon/ML_Deploy_MSCD.git /opt/ML_Deploy_MSCD

WORKDIR /opt/ML_Deploy_MSCD/section-08-deploying-with-containers/house-prices-api


# Install requirements, including from Gemfury
# ADD ./house-prices-api /opt/house-prices-api/
RUN pip install --upgrade pip

RUN ls

RUN pip install -r requirements.txt

RUN chmod +x run.sh
RUN chown -R ml-api-user:ml-api-user ./

USER ml-api-user

EXPOSE 8001

CMD ["bash", "./run.sh"]
