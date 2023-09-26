FROM python:3.7-slim

ENV PYTHONUNBUFFERED=TRUE

# RUN pip --no-cache-dir install pipenv

WORKDIR /app

COPY requirements.txt ./

RUN pip install --no-cache-dir -r requirements.txt

# COPY ["Pipfile", "Pipfile.lock", "./"]

# RUN pipenv install --system --deploy &&\	
	# rm -rf /root/.cache

COPY ["*.py", "churn-model.bin", "./"]

EXPOSE 9695

ENTRYPOINT ["gunicorn", "--bind", "0.0.0.0:9696", "churn:app"]
