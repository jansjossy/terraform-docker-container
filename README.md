PS C:\Users\janzj\terraform-docker-container\terraform-docker-container> terraform init
Terraform initialized in an empty directory!

The directory has no Terraform configuration files. You may begin working
with Terraform immediately by creating Terraform configuration files.
PS C:\Users\janzj\terraform-docker-container\terraform-docker-container> cd C:\Users\janzj\terraform-docker-container
PS C:\Users\janzj\terraform-docker-container> terraform init
Initializing the backend...
Initializing provider plugins...
- Reusing previous version of kreuzwerker/docker from the dependency lock file
- Using previously-installed kreuzwerker/docker v2.24.0

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
PS C:\Users\janzj\terraform-docker-container> terraform plan
docker_image.nginx_image: Refreshing state... [id=sha256:be69f2940aaf64fdf50c9c99420cbd57e10ee655ec7204df1c407e9af63d0cc1nginx:latest]
docker_container.nginx_container: Refreshing state... [id=7cea7748f98660fec957e62a90b9637afd71829f80c392ff7d4a9d2db858e20e]

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
-/+ destroy and then create replacement

Terraform will perform the following actions:

  # docker_container.nginx_container must be replaced
-/+ resource "docker_container" "nginx_container" {
      + bridge                                      = (known after apply)
      ~ command                                     = [
          - "nginx",
          - "-g",
          - "daemon off;",
        ] -> (known after apply)
      + container_logs                              = (known after apply)
      - cpu_shares                                  = 0 -> null
      - dns                                         = [] -> null
      - dns_opts                                    = [] -> null
      - dns_search                                  = [] -> null
      ~ entrypoint                                  = [
          - "/docker-entrypoint.sh",
        ] -> (known after apply)
      ~ env                                         = [] -> (known after apply)
      + exit_code                                   = (known after apply)
      ~ gateway                                     = "172.17.0.1" -> (known after apply)
      - group_add                                   = [] -> null
      ~ hostname                                    = "7cea7748f986" -> (known after apply)
      ~ id                                          = "7cea7748f98660fec957e62a90b9637afd71829f80c392ff7d4a9d2db858e20e" -> (known after apply)
      ~ image                                       = "sha256:be69f2940aaf64fdf50c9c99420cbd57e10ee655ec7204df1c407e9af63d0cc1" -> "nginx:latest" # forces replacement
      ~ init                                        = false -> (known after apply)
      ~ ip_address                                  = "172.17.0.2" -> (known after apply)
      ~ ip_prefix_length                            = 16 -> (known after apply)
      ~ ipc_mode                                    = "private" -> (known after apply)
      - links                                       = [] -> null
      ~ log_driver                                  = "json-file" -> (known after apply)
      - log_opts                                    = {} -> null
      - max_retry_count                             = 0 -> null
      - memory                                      = 0 -> null
      - memory_swap                                 = 0 -> null
        name                                        = "nginx-container"
      ~ network_data                                = [
          - {
              - gateway                   = "172.17.0.1"


     - global_ipv6_prefix_length = 0
              - ip_address                = "172.17.0.2"
              - ip_prefix_length          = 16
              - network_name              = "bridge"
                # (2 unchanged attributes hidden)
            },
        ] -> (known after apply)
      - network_mode                                = "bridge" -> null # forces replacement
      - privileged                                  = false -> null
      - publish_all_ports                           = false -> null
      ~ runtime                                     = "runc" -> (known after apply)
      ~ security_opts                               = [] -> (known after apply)
      ~ shm_size                                    = 64 -> (known after apply)
      ~ stop_signal                                 = "SIGQUIT" -> (known after apply)
      ~ stop_timeout                                = 0 -> (known after apply)
      - storage_opts                                = {} -> null
      - sysctls                                     = {} -> null
      - tmpfs                                       = {} -> null
        # (19 unchanged attributes hidden)

      ~ healthcheck (known after apply)

      ~ labels (known after apply)

        # (1 unchanged block hidden)
    }

Plan: 1 to add, 0 to change, 1 to destroy.

───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────── 

Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run "terraform apply" now.
PS C:\Users\janzj\terraform-docker-container> terraform apply
docker_image.nginx_image: Refreshing state... [id=sha256:be69f2940aaf64fdf50c9c99420cbd57e10ee655ec7204df1c407e9af63d0cc1nginx:latest]
docker_container.nginx_container: Refreshing state... [id=7cea7748f98660fec957e62a90b9637afd71829f80c392ff7d4a9d2db858e20e]

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
-/+ destroy and then create replacement

Terraform will perform the following actions:


# docker_container.nginx_container must be replaced
-/+ resource "docker_container" "nginx_container" {
      + bridge                                      = (known after apply)
      ~ command                                     = [
          - "nginx",
          - "-g",
          - "daemon off;",
        ] -> (known after apply)
      + container_logs                              = (known after apply)
      - cpu_shares                                  = 0 -> null
      - dns                                         = [] -> null
      - dns_opts                                    = [] -> null
      - dns_search                                  = [] -> null
      ~ entrypoint                                  = [
          - "/docker-entrypoint.sh",
        ] -> (known after apply)
      ~ env                                         = [] -> (known after apply)
      + exit_code                                   = (known after apply)
      ~ gateway                                     = "172.17.0.1" -> (known after apply)
      - group_add                                   = [] -> null
      ~ hostname                                    = "7cea7748f986" -> (known after apply)
      ~ id                                          = "7cea7748f98660fec957e62a90b9637afd71829f80c392ff7d4a9d2db858e20e" -> (known after apply)
      ~ image                                       = "sha256:be69f2940aaf64fdf50c9c99420cbd57e10ee655ec7204df1c407e9af63d0cc1" -> "nginx:latest" # forces replacement
      ~ init                                        = false -> (known after apply)
      ~ ip_address                                  = "172.17.0.2" -> (known after apply)
      ~ ip_prefix_length                            = 16 -> (known after apply)
      ~ ipc_mode                                    = "private" -> (known after apply)
      - links                                       = [] -> null
      ~ log_driver                                  = "json-file" -> (known after apply)
      - log_opts                                    = {} -> null
      - max_retry_count                             = 0 -> null
      - memory                                      = 0 -> null
      - memory_swap                                 = 0 -> null
        name                                        = "nginx-container"
      ~ network_data                                = [
          - {
              - gateway                   = "172.17.0.1"
              - global_ipv6_prefix_length = 0
              - ip_address                = "172.17.0.2"
              - ip_prefix_length          = 16
              - network_name              = "bridge"
                # (2 unchanged attributes hidden)
            },
        ] -> (known after apply)
      - network_mode                                = "bridge" -> null # forces replacement
      - privileged                                  = false -> null
      - publish_all_ports                           = false -> null
      ~ runtime                                     = "runc" -> (known after apply)
      ~ security_opts                               = [] -> (known after apply)
      ~ shm_size                                    = 64 -> (known after apply)
      ~ stop_signal                                 = "SIGQUIT" -> (known after apply)
      ~ stop_timeout                                = 0 -> (known after apply)
      - storage_opts                                = {} -> null
      - sysctls                                     = {} -> null
      - tmpfs                                       = {} -> null
        # (19 unchanged attributes hidden)

      ~ healthcheck (known after apply)

      ~ labels (known after apply)

        # (1 unchanged block hidden)
    }

Plan: 1 to add, 0 to change, 1 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

  docker_container.nginx_container: Destroying... [id=7cea7748f98660fec957e62a90b9637afd71829f80c392ff7d4a9d2db858e20e]
docker_container.nginx_container: Destruction complete after 1s
docker_container.nginx_container: Creating...
docker_container.nginx_container: Creation complete after 0s [id=fa01e9aa26621894d80df2189c4a9dfe8491a8d318bfff9d7e1437c21c01033f]

Apply complete! Resources: 1 added, 0 changed, 1 destroyed.
PS C:\Users\janzj\terraform-docker-container> docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                  NAMES
fa01e9aa2662   nginx:latest   "/docker-entrypoint.…"   15 seconds ago   Up 14 seconds   0.0.0.0:8081->80/tcp   nginx-container
PS C:\Users\janzj\terraform-docker-container> terraform state list
docker_container.nginx_container
docker_image.nginx_image
