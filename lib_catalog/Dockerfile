FROM python:3.8-slim

COPY requirements.txt /tmp/
RUN pip install -r /tmp/requirements.txt
COPY . /tmp/

WORKDIR /backend
COPY . .

CMD ["python", "manage.py", "migrate"]
CMD ["python", "manage.py", "loaddata", "bbk_data.json"]
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
