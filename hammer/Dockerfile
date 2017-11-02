FROM centos:7

MAINTAINER thomasmckay

COPY hammer.repo /etc/yum.repos.d/hammer.repo
RUN yum -y install foreman-release-scl
RUN yum clean all && yum repolist && yum update -y
RUN yum -y install \
    foreman-release-scl \
    tfm-rubygem-hammer_cli \
    tfm-rubygem-hammer_cli_katello \
    tfm-rubygem-hammer_cli_csv

RUN echo ":csv:" > /etc/hammer/cli.modules.d/csv.yml
RUN echo "  :enable_module: true" >> /etc/hammer/cli.modules.d/csv.yml

ENTRYPOINT ["hammer"]
CMD ["--help"]