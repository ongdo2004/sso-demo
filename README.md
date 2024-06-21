#introduce

SSO-Demo is a project developed as a demo according to the requirements of BlueBelt Technology company.

 The requirements are summarized as follows:

    Develop a centralized Single Sign On (SSO) system for multiple company services.
    Support various login methods (username, email, Google account, Facebook account).

Assignment link: https://docs.google.com/document/d/1150SqcaGhZ1JHf5oINaKC_YCVn8WybySCxUTKurXqE0/edit
Thank to: https://www.keycloak.org/

#Project Structure:

    ./demo: This directory contains the docker-compose files to run the application.
    ./sso-service-demo-01: This is the demo source code to simulate an arbitrary service (named sso-demo-service-01).
    ./sso-service-demo-02: This is the demo source code to simulate another arbitrary service (named sso-demo-service-02).
	

#Steps to Run the Project:

    1. Configure Local Domains:
        Since this project uses simulated domains, add the following configurations to your hosts file:

        127.0.0.1 keycloak.online
        127.0.0.1 ssodemoservice01
        127.0.0.1 ssodemoservice02

    2. Configure Docker Compose File:
        Open ./demo/docker-compose.yml and find the "extra_hosts" configuration.
        Replace <PC-ip> with your actual machine's IP address:

        extra_hosts:
          - keycloak.online:<your_pc_ip>

    3. Start Docker Containers:
        Make sure Docker and Docker Compose are installed on your system.
        Navigate to the ./demo directory and run the following command:
        Bash

        cd ./demo
		docker-compose -f postgres.yml up -d
        docker-compose up -d

    4. Access Demo Sites:
        The demo sites will be available at the following addresses:
            http://ssodemoservice01:8080/: Represents service 01.
            http://ssodemoservice02:8081/: Represents service 02.
            http://keycloak.online:9080/: Keycloak administration page.

    For detailed instructions, follow the guide at: https://github.com/ongdo2004/sso-demo.git.
    Or watch the demo video at: https://youtu.be/jZX6D6Gmn8E.