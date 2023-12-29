# Collect-Apache-Logs-with-Filebeat


Project Summary And Guide :
---------------------------

1- First, if you don't have Apache access and error logs on hand, download them from a website or other sources.

2- If the downloaded Apache logs are in deb or tar.gz format, extract them.

3- After extracting the logs from compressed files, verify their directory location in the terminal.

4- Type "sudo vim /etc/filebeat/modules.d/apache.yml.disabled" in the terminal and enter the file.

5- Initially, the Apache logs will appear with incomplete log paths and as disabled.

6- I have corrected the apache.yml file for you and published it; open it and copy the code inside, then paste it into your own apache.yml file.

7- In the apache.yml file, enter the directory where your Apache access and error logs are under "var.paths:", save, and exit the file.

8- Type "sudo filebeat modules list" in the terminal, and you will see Apache listed as disabled.

9- Again in the terminal, type "sudo filebeat modules enable apache," and when you check your filebeat modules list, "apache" will now be enabled.

10- Before running Filebeat, check the configurations in your filebeat.yml file.

11- If you want a ready configuration file, you can use the filebeat.yml file I provided as an example.

12- If configurations are okay, you can now start Filebeat.

13- Type "sudo systemctl start filebeat" in the terminal, and after the service is running, type "sudo filebeat setup -e" and wait for the logs to be indexed in Elasticsearch.

14- In Kibana, go to "Stack Management," then "Index Management," and you will see an index named "filebeat" under the "Indices" section.

15- This confirms that Apache access and error logs have been indexed in Elasticsearch.

16- After verifying that Apache logs have been indexed, Apache Logs will be ready for you in the Kibana Dashboard.

17- Once you view Apache logs in the dashboard, you can perform inspections, analyses, and edits on them.
