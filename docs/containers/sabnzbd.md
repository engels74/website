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
<tr><td><div id="tag415" onclick="CopyToClipboard('tag415');return false;" class="tag-decoration">nightly</div><div id="tag20011" onclick="CopyToClipboard('tag20011');return false;" class="tag-decoration">nightly-d45a1a4</div><div id="tag30344" onclick="CopyToClipboard('tag30344');return false;" class="tag-decoration">nightly-972f4832c1edbc1c9d056bbb71f4c29055c4c399</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d45a1a410b3ca79abe6c83ffa5e9890b63c04152" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27965872785" target="_blank">2026-06-22 15:56:03</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag31588" onclick="CopyToClipboard('tag31588');return false;" class="tag-decoration">release</div><div id="tag31454" onclick="CopyToClipboard('tag31454');return false;" class="tag-decoration">release-202cc34</div><div id="tag11269" onclick="CopyToClipboard('tag11269');return false;" class="tag-decoration">release-5.0.4</div><div id="tag4771" onclick="CopyToClipboard('tag4771');return false;" class="tag-decoration">release-v5</div><div id="tag4729" onclick="CopyToClipboard('tag4729');return false;" class="tag-decoration">release-v5.0</div><div id="tag26023" onclick="CopyToClipboard('tag26023');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/202cc3454a10a642b98e058c6c896fdb2ba9a09a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27915528970" target="_blank">2026-06-21 19:48:19</a></td></tr>
<tr><td><div id="tag27319" onclick="CopyToClipboard('tag27319');return false;" class="tag-decoration">testing</div><div id="tag29959" onclick="CopyToClipboard('tag29959');return false;" class="tag-decoration">testing-67fcfcf</div><div id="tag7013" onclick="CopyToClipboard('tag7013');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag7180" onclick="CopyToClipboard('tag7180');return false;" class="tag-decoration">testing-v5</div><div id="tag13156" onclick="CopyToClipboard('tag13156');return false;" class="tag-decoration">testing-v5.0</div><div id="tag32371" onclick="CopyToClipboard('tag32371');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/67fcfcfcc0e098be21aab02389a934401fca9d32" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27915528152" target="_blank">2026-06-21 19:48:17</a></td></tr>
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
