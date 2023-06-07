# gitlab-runner

## 🚀 Getting started

1. To deploy local GitLab runner, first run this register command:

```bash
docker container run --rm -it \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /path/to/gitlab-runner/etc:/etc/gitlab-runner \
-v /path/to/gitlab-runner/home:/home/gitlab-runner \
gitlab/gitlab-runner:latest register
```

2. You can then customize the configuration in `/path/to/gitlab-runner/etc/config.toml`
(see https://docs.gitlab.com/runner/configuration/advanced-configuration.html).

3. Then, run the following command to start the runner with the configuration setted in previous steps:

```bash
docker container run -d \
--name gitlab-runner \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /path/to/gitlab-runner/etc:/etc/gitlab-runner \
-v /path/to/gitlab-runner/home:/home/gitlab-runner \
gitlab/gitlab-runner:latest
```

> See https://docs.gitlab.com/runner/install/docker.html#install-the-docker-image-and-start-the-container
for more details.
