FROM python:3.11.7-slim

RUN set -x && \
  apt-get update && \
  apt-get install -y --no-install-recommends \
  libgomp1 \
  git \
  pkg-config \
  libhdf5-dev \
  g++ \
  python3-dev && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

COPY requirements.txt ./requirements.txt
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

CMD ["bash"]
