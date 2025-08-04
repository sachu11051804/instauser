# Use official Tomcat 10.1 with JDK 17
FROM tomcat:10.1-jdk17

# Remove default webapps
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy your WAR file and rename it to ROOT.war (auto-deploy)
COPY ROOT.war /usr/local/tomcat/webapps/ROOT.war

# ✅ Download and install PostgreSQL JDBC driver
ADD https://jdbc.postgresql.org/download/postgresql-42.7.3.jar /usr/local/tomcat/lib/

# Optional: Disable Tomcat shutdown port for security
RUN sed -i 's/<Server port="8005"/<Server port="-1"/' /usr/local/tomcat/conf/server.xml

# Expose port 8080
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]

