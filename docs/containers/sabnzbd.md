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
<tr><td><div id="tag19668" onclick="CopyToClipboard('tag19668');return false;" class="tag-decoration">nightly</div><div id="tag57" onclick="CopyToClipboard('tag57');return false;" class="tag-decoration">nightly-2762bb3</div><div id="tag28680" onclick="CopyToClipboard('tag28680');return false;" class="tag-decoration">nightly-25d20f0f08ce2078402faf0e7b281db9ceb04643</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/2762bb3e1c68b4c9d0db358724b2a8bef97ac7b1" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26360698116" target="_blank">2026-05-24 12:02:19</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag11027" onclick="CopyToClipboard('tag11027');return false;" class="tag-decoration">release</div><div id="tag30851" onclick="CopyToClipboard('tag30851');return false;" class="tag-decoration">release-5d5cbe4</div><div id="tag31111" onclick="CopyToClipboard('tag31111');return false;" class="tag-decoration">release-5.0.3</div><div id="tag15019" onclick="CopyToClipboard('tag15019');return false;" class="tag-decoration">release-v5</div><div id="tag29726" onclick="CopyToClipboard('tag29726');return false;" class="tag-decoration">release-v5.0</div><div id="tag31207" onclick="CopyToClipboard('tag31207');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5d5cbe4f1453595a65a688585076e50490ae51cf" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26360697364" target="_blank">2026-05-24 12:02:16</a></td></tr>
<tr><td><div id="tag5838" onclick="CopyToClipboard('tag5838');return false;" class="tag-decoration">testing</div><div id="tag7091" onclick="CopyToClipboard('tag7091');return false;" class="tag-decoration">testing-8cb8081</div><div id="tag1617" onclick="CopyToClipboard('tag1617');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag1031" onclick="CopyToClipboard('tag1031');return false;" class="tag-decoration">testing-v5</div><div id="tag21112" onclick="CopyToClipboard('tag21112');return false;" class="tag-decoration">testing-v5.0</div><div id="tag5557" onclick="CopyToClipboard('tag5557');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8cb8081bf0434dd07e454648cad1d85a1dabe307" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26360698426" target="_blank">2026-05-24 12:02:19</a></td></tr>
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
