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
<tr><td><div id="tag1289" onclick="CopyToClipboard('tag1289');return false;" class="tag-decoration">nightly</div><div id="tag12924" onclick="CopyToClipboard('tag12924');return false;" class="tag-decoration">nightly-4b3626e</div><div id="tag4786" onclick="CopyToClipboard('tag4786');return false;" class="tag-decoration">nightly-972f4832c1edbc1c9d056bbb71f4c29055c4c399</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/4b3626e31175453fc09107b931b31c60cf3215f2" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27987237103" target="_blank">2026-06-22 22:06:18</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag24380" onclick="CopyToClipboard('tag24380');return false;" class="tag-decoration">release</div><div id="tag29827" onclick="CopyToClipboard('tag29827');return false;" class="tag-decoration">release-202cc34</div><div id="tag31698" onclick="CopyToClipboard('tag31698');return false;" class="tag-decoration">release-5.0.4</div><div id="tag30770" onclick="CopyToClipboard('tag30770');return false;" class="tag-decoration">release-v5</div><div id="tag28295" onclick="CopyToClipboard('tag28295');return false;" class="tag-decoration">release-v5.0</div><div id="tag32404" onclick="CopyToClipboard('tag32404');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/202cc3454a10a642b98e058c6c896fdb2ba9a09a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27915528970" target="_blank">2026-06-21 19:48:19</a></td></tr>
<tr><td><div id="tag13532" onclick="CopyToClipboard('tag13532');return false;" class="tag-decoration">testing</div><div id="tag28887" onclick="CopyToClipboard('tag28887');return false;" class="tag-decoration">testing-67fcfcf</div><div id="tag26199" onclick="CopyToClipboard('tag26199');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag13589" onclick="CopyToClipboard('tag13589');return false;" class="tag-decoration">testing-v5</div><div id="tag3629" onclick="CopyToClipboard('tag3629');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23838" onclick="CopyToClipboard('tag23838');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/67fcfcfcc0e098be21aab02389a934401fca9d32" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27915528152" target="_blank">2026-06-21 19:48:17</a></td></tr>
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
