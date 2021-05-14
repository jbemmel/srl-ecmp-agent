FROM registry.srlinux.dev/pub/srlinux:latest

# --chown=srlinux:srlinux
# COPY ./appmgr/ /etc/opt/srlinux/appmgr/ # doesn't stick
COPY ./appmgr/ /home/appmgr

COPY 42_sr_copy_custom_appmgr.sh /opt/srlinux/bin/bootscript/

# Add Paris traceroute
COPY --from=paris-traceroute /usr/local/bin/paris-* /usr/local/bin/
COPY --from=paris-traceroute /usr/local/lib/* /usr/local/lib/

# Using a build arg to set the release tag, set a default for running docker build manually
ARG SRL_AUTO_CONFIG_RELEASE="[custom build]"
ENV SRL_AUTO_CONFIG_RELEASE=$SRL_AUTO_CONFIG_RELEASE
