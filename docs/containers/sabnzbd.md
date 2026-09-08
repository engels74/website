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
<tr><td><div id="tag13895" onclick="CopyToClipboard('tag13895');return false;" class="tag-decoration">nightly</div><div id="tag22567" onclick="CopyToClipboard('tag22567');return false;" class="tag-decoration">nightly-386e142</div><div id="tag23957" onclick="CopyToClipboard('tag23957');return false;" class="tag-decoration">nightly-9d365facaa1a841ae691277e5f26f189960c26ca</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/386e1422562b7d3dda59ba4f22e36bddf11199e6" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217793663" target="_blank">2026-09-08 10:53:14</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29043" onclick="CopyToClipboard('tag29043');return false;" class="tag-decoration">release</div><div id="tag16210" onclick="CopyToClipboard('tag16210');return false;" class="tag-decoration">release-20eb037</div><div id="tag21160" onclick="CopyToClipboard('tag21160');return false;" class="tag-decoration">release-5.1.2</div><div id="tag12733" onclick="CopyToClipboard('tag12733');return false;" class="tag-decoration">release-v5</div><div id="tag5606" onclick="CopyToClipboard('tag5606');return false;" class="tag-decoration">release-v5.1</div><div id="tag21204" onclick="CopyToClipboard('tag21204');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/20eb037ae7e9a857774d5d9beecfa51d2fded6f7" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33969812936" target="_blank">2026-09-05 13:45:18</a></td></tr>
<tr><td><div id="tag24491" onclick="CopyToClipboard('tag24491');return false;" class="tag-decoration">testing</div><div id="tag6417" onclick="CopyToClipboard('tag6417');return false;" class="tag-decoration">testing-fc03f0f</div><div id="tag12472" onclick="CopyToClipboard('tag12472');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag21945" onclick="CopyToClipboard('tag21945');return false;" class="tag-decoration">testing-v5</div><div id="tag5560" onclick="CopyToClipboard('tag5560');return false;" class="tag-decoration">testing-v5.1</div><div id="tag20838" onclick="CopyToClipboard('tag20838');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/fc03f0fa807a0aae7ff1c8e27d692f150745a6bb" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33969811147" target="_blank">2026-09-05 13:45:16</a></td></tr>
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
