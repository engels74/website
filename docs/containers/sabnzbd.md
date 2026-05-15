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
<tr><td><div id="tag26260" onclick="CopyToClipboard('tag26260');return false;" class="tag-decoration">nightly</div><div id="tag9498" onclick="CopyToClipboard('tag9498');return false;" class="tag-decoration">nightly-b6008b8</div><div id="tag17353" onclick="CopyToClipboard('tag17353');return false;" class="tag-decoration">nightly-60f555117c78466704bcb82b22cc5027944e8139</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/b6008b87757315dad2a49fda4caba773ea001958" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932486590" target="_blank">2026-05-15 17:43:01</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16033" onclick="CopyToClipboard('tag16033');return false;" class="tag-decoration">release</div><div id="tag24524" onclick="CopyToClipboard('tag24524');return false;" class="tag-decoration">release-5cde00f</div><div id="tag14340" onclick="CopyToClipboard('tag14340');return false;" class="tag-decoration">release-5.0.3</div><div id="tag17991" onclick="CopyToClipboard('tag17991');return false;" class="tag-decoration">release-v5</div><div id="tag18825" onclick="CopyToClipboard('tag18825');return false;" class="tag-decoration">release-v5.0</div><div id="tag28403" onclick="CopyToClipboard('tag28403');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5cde00fb9e68b414c8c07d3ec49b7697fdc1424b" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25925933814" target="_blank">2026-05-15 15:22:32</a></td></tr>
<tr><td><div id="tag31009" onclick="CopyToClipboard('tag31009');return false;" class="tag-decoration">testing</div><div id="tag7311" onclick="CopyToClipboard('tag7311');return false;" class="tag-decoration">testing-af66d6f</div><div id="tag31918" onclick="CopyToClipboard('tag31918');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag12181" onclick="CopyToClipboard('tag12181');return false;" class="tag-decoration">testing-v5</div><div id="tag14979" onclick="CopyToClipboard('tag14979');return false;" class="tag-decoration">testing-v5.0</div><div id="tag1458" onclick="CopyToClipboard('tag1458');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/af66d6fffe436c78f9fde0b2f793e40f60acbc26" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25925933927" target="_blank">2026-05-15 15:22:33</a></td></tr>
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
