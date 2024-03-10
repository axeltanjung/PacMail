FROM python:3.10

# Menyalin requirement.txt dan menginstall dependencies
COPY ./requirements.txt /
RUN pip install -r /requirements.txt

# Menyalin api.py ke dalam container
COPY ./api.py /

# Menjalankan perintah saat container dijalankan
CMD ["python3", "api.py"]