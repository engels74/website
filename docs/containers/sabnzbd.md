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
<tr><td><div id="tag14617" onclick="CopyToClipboard('tag14617');return false;" class="tag-decoration">nightly</div><div id="tag27682" onclick="CopyToClipboard('tag27682');return false;" class="tag-decoration">nightly-386e142</div><div id="tag29666" onclick="CopyToClipboard('tag29666');return false;" class="tag-decoration">nightly-9d365facaa1a841ae691277e5f26f189960c26ca</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/386e1422562b7d3dda59ba4f22e36bddf11199e6" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217793663" target="_blank">2026-09-08 10:53:14</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag8000" onclick="CopyToClipboard('tag8000');return false;" class="tag-decoration">release</div><div id="tag32299" onclick="CopyToClipboard('tag32299');return false;" class="tag-decoration">release-c1c5935</div><div id="tag11756" onclick="CopyToClipboard('tag11756');return false;" class="tag-decoration">release-5.1.3</div><div id="tag17152" onclick="CopyToClipboard('tag17152');return false;" class="tag-decoration">release-v5</div><div id="tag30711" onclick="CopyToClipboard('tag30711');return false;" class="tag-decoration">release-v5.1</div><div id="tag21104" onclick="CopyToClipboard('tag21104');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/c1c59358e8edf6d20a713366918f60bce5c703dc" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217811317" target="_blank">2026-09-08 10:53:25</a></td></tr>
<tr><td><div id="tag32097" onclick="CopyToClipboard('tag32097');return false;" class="tag-decoration">testing</div><div id="tag19256" onclick="CopyToClipboard('tag19256');return false;" class="tag-decoration">testing-aaf9a5e</div><div id="tag21906" onclick="CopyToClipboard('tag21906');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag7384" onclick="CopyToClipboard('tag7384');return false;" class="tag-decoration">testing-v5</div><div id="tag19179" onclick="CopyToClipboard('tag19179');return false;" class="tag-decoration">testing-v5.1</div><div id="tag22514" onclick="CopyToClipboard('tag22514');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aaf9a5e7b4ddc42d99b7756dff47a2f65e9f481b" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217797894" target="_blank">2026-09-08 10:53:17</a></td></tr>
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
