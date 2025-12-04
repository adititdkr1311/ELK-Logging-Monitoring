Implementing ELK stack using docker-compose for monitoring springboot application 

Execution Steps:

  Application deployment 
	      - spin ec2 instance 
		    - install docker 
		    - start docker 
		    - install docker-compose 
        - clone repo  
        - Run docker file to build image : Call from jenkinsfile 
		           - application container will have 
                    - volume mapping    :  for storing application logs , which will be shared by logstash service as well 
                    - port 				:  for accessing the application 
		  
		  
   ELK stack deployment 
	     - Using docker compose up 
		 
		      service 1 - logstash
			                 - volume mapping 
				               - application logs 
						           - conf.d  
						           - This file has info 
							             - where is the log path 
								           - what pattern to search 
								           - elastic search container details to send the parsed logs to 
			  service 2 - elastic search
			  service 3 - kibana
   

     -- Access Kibana using 
	     <public-ip-address>:5601

     -- release resources
	     - docker compose down 
		   - docker system prune --all 
