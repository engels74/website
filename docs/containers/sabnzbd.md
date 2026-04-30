---
hide:
  - toc
title: engels74/sabnzbd
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/sabnzbd){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/sabnzbd){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://sabnzbd.org){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/sabnzbd.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [SABnzbd](https://hotio.dev/containers/sabnzbd) Docker image, that includes ffprobe, at `/app/bin/ffprobe`. Useful for scripts.

<div id="tags-table">
  <table>
    <thead>
      <tr>
        <th>Tags <span class="twemoji" title="Click Tag to Copy"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M11 9h2V7h-2m1 13c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8m0-18A10 10 0 0 0 2 12a10 10 0 0 0 10 10 10 10 0 0 0 10-10A10 10 0 0 0 12 2m-1 15h2v-6h-2z"></path></svg></span></th>
        <th>Description</th>
        <th>Commit</th>
        <th>Last Updated</th>
      </tr>
    </thead>
    <tbody id="tags-table-body">
<tr><td><div id="tag22406" onclick="CopyToClipboard('tag22406');return false;" class="tag-decoration">nightly</div><div id="tag5280" onclick="CopyToClipboard('tag5280');return false;" class="tag-decoration">nightly-65ad17f</div><div id="tag21086" onclick="CopyToClipboard('tag21086');return false;" class="tag-decoration">nightly-b84fd1526aeb4526be0498f90e52bf92922812c3</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/65ad17f78f716a33ff9752ab6884d068c663b08c" target="_blank">Version update: 2cb598309d56588bfb5aff1aad48ec738e2ad0a5 => b84fd1526aeb4526be0498f90e52bf92922812c3</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25153981744" target="_blank">2026-04-30 07:52:22</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15399" onclick="CopyToClipboard('tag15399');return false;" class="tag-decoration">release</div><div id="tag29475" onclick="CopyToClipboard('tag29475');return false;" class="tag-decoration">release-7db252b</div><div id="tag30864" onclick="CopyToClipboard('tag30864');return false;" class="tag-decoration">release-4.5.5</div><div id="tag13196" onclick="CopyToClipboard('tag13196');return false;" class="tag-decoration">release-v4</div><div id="tag2125" onclick="CopyToClipboard('tag2125');return false;" class="tag-decoration">release-v4.5</div><div id="tag26336" onclick="CopyToClipboard('tag26336');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7db252bf08540717a7aa74602c9d639c04d3ad2e" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552121945" target="_blank">2026-04-17 06:53:48</a></td></tr>
<tr><td><div id="tag426" onclick="CopyToClipboard('tag426');return false;" class="tag-decoration">testing</div><div id="tag15234" onclick="CopyToClipboard('tag15234');return false;" class="tag-decoration">testing-7cfcbd6</div><div id="tag1772" onclick="CopyToClipboard('tag1772');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag12720" onclick="CopyToClipboard('tag12720');return false;" class="tag-decoration">testing-v4</div><div id="tag12244" onclick="CopyToClipboard('tag12244');return false;" class="tag-decoration">testing-v4.5</div><div id="tag13669" onclick="CopyToClipboard('tag13669');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7cfcbd6176ce3f990aee507d9ef2284ac757746b" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552122310" target="_blank">2026-04-17 06:53:49</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name sabnzbd \
        -p 8080:8080 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e WEBUI_PORTS="8080/tcp,8080/udp" \
        -e ARGS="" \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/sabnzbd
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      sabnzbd:
        container_name: sabnzbd
        image: ghcr.io/engels74/sabnzbd
        ports:
          - "8080:8080"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=8080/tcp,8080/udp
          - ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

--8<-- "includes/wireguard.md"
