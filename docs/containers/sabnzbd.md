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
<tr><td><div id="tag28999" onclick="CopyToClipboard('tag28999');return false;" class="tag-decoration">nightly</div><div id="tag6145" onclick="CopyToClipboard('tag6145');return false;" class="tag-decoration">nightly-d3bc18f</div><div id="tag743" onclick="CopyToClipboard('tag743');return false;" class="tag-decoration">nightly-90798e5e4dcbd2e45bc0aa36f95de482e08b8cea</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d3bc18fcb877ea7bb12bab9202c3c4c4d1c6fa76" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25713907722" target="_blank">2026-05-12 04:44:32</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag32708" onclick="CopyToClipboard('tag32708');return false;" class="tag-decoration">release</div><div id="tag27664" onclick="CopyToClipboard('tag27664');return false;" class="tag-decoration">release-4860033</div><div id="tag2474" onclick="CopyToClipboard('tag2474');return false;" class="tag-decoration">release-5.0.1</div><div id="tag5409" onclick="CopyToClipboard('tag5409');return false;" class="tag-decoration">release-v5</div><div id="tag32582" onclick="CopyToClipboard('tag32582');return false;" class="tag-decoration">release-v5.0</div><div id="tag18896" onclick="CopyToClipboard('tag18896');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4860033077730c63ff750af32c2e02fc3ce04fa9" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25713910671" target="_blank">2026-05-12 04:44:38</a></td></tr>
<tr><td><div id="tag26766" onclick="CopyToClipboard('tag26766');return false;" class="tag-decoration">testing</div><div id="tag4746" onclick="CopyToClipboard('tag4746');return false;" class="tag-decoration">testing-b6bc765</div><div id="tag18171" onclick="CopyToClipboard('tag18171');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag22734" onclick="CopyToClipboard('tag22734');return false;" class="tag-decoration">testing-v5</div><div id="tag29864" onclick="CopyToClipboard('tag29864');return false;" class="tag-decoration">testing-v5.0</div><div id="tag5551" onclick="CopyToClipboard('tag5551');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b6bc7659612c8e05b6e39587a09d2ac4aba4c770" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25713913622" target="_blank">2026-05-12 04:44:44</a></td></tr>
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
