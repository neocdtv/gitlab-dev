FROM docker:20.10.12-dind as dind

FROM gitlab/gitlab-runner:latest
COPY --from=dind /usr/local/bin/docker /usr/local/bin/
VOLUME ["/etc/gitlab-runner", "/home/gitlab-runner"]
ENTRYPOINT ["/usr/bin/dumb-init", "/entrypoint"]
CMD ["run", "--user=gitlab-runner", "--working-directory=/home/gitlab-runner"]

