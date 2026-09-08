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
<tr><td><div id="tag13924" onclick="CopyToClipboard('tag13924');return false;" class="tag-decoration">nightly</div><div id="tag963" onclick="CopyToClipboard('tag963');return false;" class="tag-decoration">nightly-d4db6ad</div><div id="tag10459" onclick="CopyToClipboard('tag10459');return false;" class="tag-decoration">nightly-0561dca19a306a0d63c3e80cbdc290d989ee0554</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d4db6ad3cfd2454247f7ee972e686f26be47e341" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34281997695" target="_blank">2026-09-08 21:41:30</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16861" onclick="CopyToClipboard('tag16861');return false;" class="tag-decoration">release</div><div id="tag30872" onclick="CopyToClipboard('tag30872');return false;" class="tag-decoration">release-c1c5935</div><div id="tag20105" onclick="CopyToClipboard('tag20105');return false;" class="tag-decoration">release-5.1.3</div><div id="tag21695" onclick="CopyToClipboard('tag21695');return false;" class="tag-decoration">release-v5</div><div id="tag4690" onclick="CopyToClipboard('tag4690');return false;" class="tag-decoration">release-v5.1</div><div id="tag6133" onclick="CopyToClipboard('tag6133');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/c1c59358e8edf6d20a713366918f60bce5c703dc" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217811317" target="_blank">2026-09-08 10:53:25</a></td></tr>
<tr><td><div id="tag26771" onclick="CopyToClipboard('tag26771');return false;" class="tag-decoration">testing</div><div id="tag6715" onclick="CopyToClipboard('tag6715');return false;" class="tag-decoration">testing-aaf9a5e</div><div id="tag10529" onclick="CopyToClipboard('tag10529');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag26475" onclick="CopyToClipboard('tag26475');return false;" class="tag-decoration">testing-v5</div><div id="tag31141" onclick="CopyToClipboard('tag31141');return false;" class="tag-decoration">testing-v5.1</div><div id="tag12521" onclick="CopyToClipboard('tag12521');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aaf9a5e7b4ddc42d99b7756dff47a2f65e9f481b" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34217797894" target="_blank">2026-09-08 10:53:17</a></td></tr>
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
