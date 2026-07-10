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
<tr><td><div id="tag1542" onclick="CopyToClipboard('tag1542');return false;" class="tag-decoration">nightly</div><div id="tag28385" onclick="CopyToClipboard('tag28385');return false;" class="tag-decoration">nightly-167ac01</div><div id="tag20333" onclick="CopyToClipboard('tag20333');return false;" class="tag-decoration">nightly-a2ac2b04359b4f3ec8d362baf88b002741e2bd3b</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/167ac011126aab7015b66924209d4982756771bd" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29090911113" target="_blank">2026-07-10 11:55:09</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag19776" onclick="CopyToClipboard('tag19776');return false;" class="tag-decoration">release</div><div id="tag31716" onclick="CopyToClipboard('tag31716');return false;" class="tag-decoration">release-aa1692b</div><div id="tag439" onclick="CopyToClipboard('tag439');return false;" class="tag-decoration">release-5.0.4</div><div id="tag14678" onclick="CopyToClipboard('tag14678');return false;" class="tag-decoration">release-v5</div><div id="tag16560" onclick="CopyToClipboard('tag16560');return false;" class="tag-decoration">release-v5.0</div><div id="tag12890" onclick="CopyToClipboard('tag12890');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aa1692b699b5339ee61eccad93ca9f3459641ddd" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979413673" target="_blank">2026-07-08 22:13:28</a></td></tr>
<tr><td><div id="tag30386" onclick="CopyToClipboard('tag30386');return false;" class="tag-decoration">testing</div><div id="tag13526" onclick="CopyToClipboard('tag13526');return false;" class="tag-decoration">testing-5fd6272</div><div id="tag31389" onclick="CopyToClipboard('tag31389');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag19413" onclick="CopyToClipboard('tag19413');return false;" class="tag-decoration">testing-v5</div><div id="tag28089" onclick="CopyToClipboard('tag28089');return false;" class="tag-decoration">testing-v5.0</div><div id="tag7190" onclick="CopyToClipboard('tag7190');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5fd627228d81b49e236e2a338d01d89f99664375" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979412430" target="_blank">2026-07-08 22:13:27</a></td></tr>
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
