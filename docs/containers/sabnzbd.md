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
<tr><td><div id="tag6752" onclick="CopyToClipboard('tag6752');return false;" class="tag-decoration">nightly</div><div id="tag25514" onclick="CopyToClipboard('tag25514');return false;" class="tag-decoration">nightly-c86333c</div><div id="tag20105" onclick="CopyToClipboard('tag20105');return false;" class="tag-decoration">nightly-adde7b961cdc21bfd43b4221209c895d8c788e8c</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c86333c2349cde44ff8947cf05003600c4b10578" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32144141644" target="_blank">2026-08-18 13:44:40</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag2943" onclick="CopyToClipboard('tag2943');return false;" class="tag-decoration">release</div><div id="tag22426" onclick="CopyToClipboard('tag22426');return false;" class="tag-decoration">release-db59e20</div><div id="tag3232" onclick="CopyToClipboard('tag3232');return false;" class="tag-decoration">release-5.1.1</div><div id="tag19751" onclick="CopyToClipboard('tag19751');return false;" class="tag-decoration">release-v5</div><div id="tag14521" onclick="CopyToClipboard('tag14521');return false;" class="tag-decoration">release-v5.1</div><div id="tag29474" onclick="CopyToClipboard('tag29474');return false;" class="tag-decoration">release-v5.1.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/db59e2014720f7b35c0aa31c55fabd20513d3368" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32161076498" target="_blank">2026-08-18 16:34:58</a></td></tr>
<tr><td><div id="tag15282" onclick="CopyToClipboard('tag15282');return false;" class="tag-decoration">testing</div><div id="tag13690" onclick="CopyToClipboard('tag13690');return false;" class="tag-decoration">testing-9f1ec6e</div><div id="tag12082" onclick="CopyToClipboard('tag12082');return false;" class="tag-decoration">testing-5.1.0</div><div id="tag4782" onclick="CopyToClipboard('tag4782');return false;" class="tag-decoration">testing-v5</div><div id="tag23951" onclick="CopyToClipboard('tag23951');return false;" class="tag-decoration">testing-v5.1</div><div id="tag24809" onclick="CopyToClipboard('tag24809');return false;" class="tag-decoration">testing-v5.1.0</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/9f1ec6e81ff3a769acf33049c8626b20054d4413" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32144141240" target="_blank">2026-08-18 13:44:39</a></td></tr>
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
