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
<tr><td><div id="tag26297" onclick="CopyToClipboard('tag26297');return false;" class="tag-decoration">nightly</div><div id="tag16710" onclick="CopyToClipboard('tag16710');return false;" class="tag-decoration">nightly-dc19eba</div><div id="tag1855" onclick="CopyToClipboard('tag1855');return false;" class="tag-decoration">nightly-83d167415a0fd0c4c57b6bdc9407836ef7b2cc13</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/dc19eba69814549c7745cd5ad8e00ede2569c250" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27150230236" target="_blank">2026-06-08 15:59:42</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag28263" onclick="CopyToClipboard('tag28263');return false;" class="tag-decoration">release</div><div id="tag27273" onclick="CopyToClipboard('tag27273');return false;" class="tag-decoration">release-bcf36ce</div><div id="tag13802" onclick="CopyToClipboard('tag13802');return false;" class="tag-decoration">release-5.0.3</div><div id="tag14208" onclick="CopyToClipboard('tag14208');return false;" class="tag-decoration">release-v5</div><div id="tag5991" onclick="CopyToClipboard('tag5991');return false;" class="tag-decoration">release-v5.0</div><div id="tag18882" onclick="CopyToClipboard('tag18882');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/bcf36cef7a746f9ef94e609755b9263b9a747688" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710781564" target="_blank">2026-05-31 11:01:09</a></td></tr>
<tr><td><div id="tag24767" onclick="CopyToClipboard('tag24767');return false;" class="tag-decoration">testing</div><div id="tag1783" onclick="CopyToClipboard('tag1783');return false;" class="tag-decoration">testing-009193c</div><div id="tag2202" onclick="CopyToClipboard('tag2202');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag21016" onclick="CopyToClipboard('tag21016');return false;" class="tag-decoration">testing-v5</div><div id="tag25041" onclick="CopyToClipboard('tag25041');return false;" class="tag-decoration">testing-v5.0</div><div id="tag29909" onclick="CopyToClipboard('tag29909');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/009193c9e6c31de8f8cdff399b7f16aa7f6beaaf" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710782493" target="_blank">2026-05-31 11:01:11</a></td></tr>
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
