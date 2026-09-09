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
<tr><td><div id="tag17527" onclick="CopyToClipboard('tag17527');return false;" class="tag-decoration">nightly</div><div id="tag21312" onclick="CopyToClipboard('tag21312');return false;" class="tag-decoration">nightly-2ce5cb9</div><div id="tag7292" onclick="CopyToClipboard('tag7292');return false;" class="tag-decoration">nightly-29699890d5d55b83680d679e18aa734d90663b07</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/2ce5cb9d0e7f1cfc5b2537c52dda2a908fa4f137" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34388657425" target="_blank">2026-09-09 18:22:59</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag13942" onclick="CopyToClipboard('tag13942');return false;" class="tag-decoration">release</div><div id="tag2458" onclick="CopyToClipboard('tag2458');return false;" class="tag-decoration">release-c1c5935</div><div id="tag7798" onclick="CopyToClipboard('tag7798');return false;" class="tag-decoration">release-5.1.3</div><div id="tag15252" onclick="CopyToClipboard('tag15252');return false;" class="tag-decoration">release-v5</div><div id="tag13332" onclick="CopyToClipboard('tag13332');return false;" class="tag-decoration">release-v5.1</div><div id="tag20435" onclick="CopyToClipboard('tag20435');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/c1c59358e8edf6d20a713366918f60bce5c703dc" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217811317" target="_blank">2026-09-08 10:53:25</a></td></tr>
<tr><td><div id="tag2696" onclick="CopyToClipboard('tag2696');return false;" class="tag-decoration">testing</div><div id="tag12834" onclick="CopyToClipboard('tag12834');return false;" class="tag-decoration">testing-aaf9a5e</div><div id="tag17683" onclick="CopyToClipboard('tag17683');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag8122" onclick="CopyToClipboard('tag8122');return false;" class="tag-decoration">testing-v5</div><div id="tag22246" onclick="CopyToClipboard('tag22246');return false;" class="tag-decoration">testing-v5.1</div><div id="tag18455" onclick="CopyToClipboard('tag18455');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aaf9a5e7b4ddc42d99b7756dff47a2f65e9f481b" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217797894" target="_blank">2026-09-08 10:53:17</a></td></tr>
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
