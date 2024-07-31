# Interview_prep
### Interview Questions and Answers

1. **Difference between GIT and SVN?**
   - **GIT**:
     - Distributed version control system.
     - Each user has a complete local copy of the repository.
     - Supports offline work.
     - Faster operations due to local repository.
     - Better branching and merging capabilities.
   - **SVN**:
     - Centralized version control system.
     - Single central repository.
     - Requires network access for most operations.
     - Branching and merging can be more complex.

2. **Conflicts you have faced in git?**
   - Merge conflicts during pull requests.
   - Conflicts due to simultaneous edits on the same lines of code.
   - Rebase conflicts when integrating changes from different branches.
   - Resolving binary file conflicts.

3. **What is git rebase?**
   - Git rebase is a way to integrate changes from one branch into another. It moves or combines a sequence of commits to a new base commit, updating the commit history.

4. **Difference between rebase and merge?**
   - **Rebase**:
     - Rewrites commit history.
     - Creates a linear history.
     - Can make it seem like changes were made sequentially.
   - **Merge**:
     - Combines the histories of two branches.
     - Retains the history of both branches.
     - Adds a merge commit.

5. **Difference between git fetch and git pull?**
   - **Git Fetch**:
     - Downloads changes from the remote repository.
     - Does not integrate changes into the working directory.
   - **Git Pull**:
     - Fetches changes and immediately integrates them into the current branch.
     - Combines fetch and merge.

6. **Will git pull pull all branches or the particular branch?**
   - Git pull only affects the currently checked-out branch.

7. **What activities you do in Jenkins?**
   - Setting up CI/CD pipelines.
   - Configuring build jobs.
   - Integrating with version control systems.
   - Managing plugins and dependencies.
   - Monitoring builds and deployments.
   - Automating tests and deployments.

8. **How to setup master-slave for Jenkins? What advantage do you get in master-slave?**
   - **Setup**:
     - Configure Jenkins master.
     - Add new nodes (slaves) from Jenkins master UI.
     - Set up SSH connections or other methods for slave communication.
   - **Advantages**:
     - Distributes build load.
     - Improves build performance.
     - Isolates build environments.
     - Provides fault tolerance.

9. **How to add slaves automatically in Jenkins cluster?**
   - Use Jenkins plugins like Kubernetes Plugin, Swarm Plugin, or EC2 Plugin.
   - Configure auto-scaling policies in cloud environments.

10. **What kind of authentication process are you using in Jenkins? Difference between role-based and project-based access?**
    - Using Jenkins’ own user database, LDAP, or OAuth for authentication.
    - **Role-Based Access**:
      - Assigns roles with permissions across Jenkins.
    - **Project-Based Access**:
      - Grants permissions specific to individual projects.

11. **How you handle Jenkins backup?**
    - Regularly back up Jenkins home directory.
    - Use plugins like ThinBackup or Periodic Backup.
    - Store backups in a secure, remote location.

12. **What are the types of pipelines?**
    - **Declarative Pipeline**:
      - Simplified syntax.
      - Easier to read and maintain.
    - **Scripted Pipeline**:
      - More flexible.
      - Uses Groovy syntax.

13. **Can you write Jenkins pipeline for building the code and pushing it to Nexus repository?**
    ```groovy
    pipeline {
        agent any
        stages {
            stage('Build') {
                steps {
                    sh 'mvn clean install'
                }
            }
            stage('Publish to Nexus') {
                steps {
                    sh 'mvn deploy'
                }
            }
        }
    }
    ```

14. **What are phases in Maven?**
    - Validate, Compile, Test, Package, Verify, Install, Deploy.

15. **Why does Maven take less time the second time?**
    - Caches dependencies locally.
    - Skips unchanged steps due to incremental builds.

16. **Difference between web server and application server?**
    - **Web Server**:
      - Serves static content (HTML, CSS, JS).
    - **Application Server**:
      - Serves dynamic content.
      - Manages business logic and application functionalities.

17. **Purchasing options in EC2?**
    - On-Demand Instances.
    - Reserved Instances.
    - Spot Instances.
    - Savings Plans.
    - Dedicated Hosts/Instances.

18. **Difference between spot instance and on-demand instances? What are reserved instances?**
    - **Spot Instances**:
      - Bidding model.
      - Can be terminated by AWS.
    - **On-Demand Instances**:
      - Pay-as-you-go.
      - No long-term commitment.
    - **Reserved Instances**:
      - One- or three-year commitment.
      - Lower hourly rate.

19. **Got alert that Linux file system is full. How would you increase it?**
    - Clear unnecessary files.
    - Resize the partition if using LVM.
    - Attach and mount new storage.

20. **What all file system types are there in Linux?**
    - Ext4, XFS, Btrfs, ZFS, etc.

21. **I have lost SSH key for EC2 instance. How to login on server now?**
    - Use AWS Systems Manager (SSM).
    - Detach the root volume and attach it to another instance to edit authorized keys.
    - Use EC2 Instance Connect (if enabled).

22. **Difference between SG and NACL?**
    - **Security Groups (SG)**:
      - Stateful.
      - Instance-level security.
    - **Network ACLs (NACL)**:
      - Stateless.
      - Subnet-level security.

23. **Have you used serverless services in AWS?**
    - Examples: AWS Lambda, DynamoDB, API Gateway.

24. **What is major difference between ALB and NLB? What are listeners in LB? Ports and protocols in LBs.**
    - **ALB**:
      - Application layer (HTTP/HTTPS).
    - **NLB**:
      - Network layer (TCP/UDP).
    - **Listeners**:
      - Check incoming traffic ports and protocols.
      - Route based on rules.

25. **How to connect 20+ VPCs to each other?**
    - Use AWS Transit Gateway.
    - Use VPC Peering.

26. **What are storage classes available in S3 and difference?**
    - Standard, Standard-IA, One Zone-IA, Glacier, Glacier Deep Archive, etc.

27. **How to access objects which are stored in Glacier?**
    - Initiate a restore request.
    - Specify retrieval options (Expedited, Standard, Bulk).

28. **Difference between IAM roles and policies?**
    - **IAM Roles**:
      - Assign permissions to AWS services.
    - **Policies**:
      - Define permissions.
      - Attached to users, groups, or roles.

29. **What kind of work have you done on CloudWatch and SNS?**
    - Monitoring and logging with CloudWatch.
    - Setting up alarms.
    - Using SNS for notifications and integrations.

30. **What is Route53? What is HOSTZONE? What are record sets available in DNS? Which record do we use for Load balancer?**
    - **Route53**:
      - DNS web service.
    - **HOSTZONE**:
      - Container for DNS records.
    - **Record Sets**:
      - A, AAAA, CNAME, MX, TXT, etc.
      - Use A or CNAME for load balancers.

31. **How to replace CPU utilization with memory utilization in a file (Shell Scripting)?**
    ```sh
    sed -i 's/CPU utilization/Memory utilization/g' filename
    ```

32. **How to log in to a Docker container?**
    - `docker exec -it <container_id> /bin/bash`

33. **Can we install vim in a running container?**
    - Yes, `docker exec -it <container_id> apt-get update && apt-get install vim`

34. **Make sure Jenkins service should be running after start and stop of container. How would you configure it?**
    - Use a process manager like supervisord.
    - Ensure Jenkins is set to start on boot.

35. **What is backend in Terraform?**
    - Defines where Terraform state is stored.
    - Types: local, remote (e.g., S3).

36. **What are resources you have launched using Terraform?**
    - Examples: EC2 instances, VPCs, RDS, IAM roles, S3 buckets.

37. **What are different objects in K8s?**
    - Pods, Services, Deployments, StatefulSets, ConfigMaps, Secrets, etc.

38. **Difference between ClusterIP and NodePort?**
    - **ClusterIP**:
      - Internal service within the cluster.
    - **NodePort**:
      - Exposes service on a static port on each node.

39. **When would you use LoadBalancer service?**
    - For external access to services with automatic load balancing.

40. **How are you managing rollbacks?**
    - Using versioned deployments.
    - Using Helm for Kubernetes.
    - Utilizing automated pipeline rollbacks.

41. **What is blue-green deployment?**
    - Technique to deploy new versions alongside old versions.
    - Traffic is switched to the new version once verified.

