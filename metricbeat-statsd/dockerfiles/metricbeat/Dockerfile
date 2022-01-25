FROM docker.elastic.co/beats/metricbeat:7.16.3
COPY --chown=root:metricbeat metricbeat.yml /usr/share/metricbeat/metricbeat.yml
# RUN metricbeat modules enable airflow