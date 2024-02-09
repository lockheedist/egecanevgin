# egecanevgin

---
- name: Filebeat Kurulumu ve Yapılandırması
  hosts: all
  become: yes
  vars:
    filebeat_rpm_url: "https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.10.0-x86_64.rpm"
    filebeat_config_template: "filebeat.yml.j2"
    filebeat_config_path: "/etc/filebeat/filebeat.yml"

  tasks:
    - name: Filebeat RPM dosyasını /opt dizinine indir
      get_url:
        url: "{{ filebeat_rpm_url }}"
        dest: "/opt/filebeat.rpm"

    - name: Filebeat paketini kur
      yum:
        nam
