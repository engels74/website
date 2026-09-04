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
<tr><td><div id="tag14120" onclick="CopyToClipboard('tag14120');return false;" class="tag-decoration">nightly</div><div id="tag12463" onclick="CopyToClipboard('tag12463');return false;" class="tag-decoration">nightly-2b18b76</div><div id="tag2842" onclick="CopyToClipboard('tag2842');return false;" class="tag-decoration">nightly-d25d857fc4c6d1d7c7bf9fffb718074d50cda325</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b18b763eccb9bd5a186307b33531bc1400d6a12" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33877198193" target="_blank">2026-09-04 13:16:57</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16861" onclick="CopyToClipboard('tag16861');return false;" class="tag-decoration">release</div><div id="tag19411" onclick="CopyToClipboard('tag19411');return false;" class="tag-decoration">release-5da462e</div><div id="tag24568" onclick="CopyToClipboard('tag24568');return false;" class="tag-decoration">release-5.1.2</div><div id="tag5120" onclick="CopyToClipboard('tag5120');return false;" class="tag-decoration">release-v5</div><div id="tag16950" onclick="CopyToClipboard('tag16950');return false;" class="tag-decoration">release-v5.1</div><div id="tag11181" onclick="CopyToClipboard('tag11181');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5da462ec75174d481f861cdd3b553e78d3f6237c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33803892915" target="_blank">2026-09-03 20:43:08</a></td></tr>
<tr><td><div id="tag25690" onclick="CopyToClipboard('tag25690');return false;" class="tag-decoration">testing</div><div id="tag16793" onclick="CopyToClipboard('tag16793');return false;" class="tag-decoration">testing-b9cc709</div><div id="tag11313" onclick="CopyToClipboard('tag11313');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag14665" onclick="CopyToClipboard('tag14665');return false;" class="tag-decoration">testing-v5</div><div id="tag14255" onclick="CopyToClipboard('tag14255');return false;" class="tag-decoration">testing-v5.1</div><div id="tag11402" onclick="CopyToClipboard('tag11402');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b9cc709a37cfdcbf2531266baac2c22025a935f7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33803889022" target="_blank">2026-09-03 20:43:06</a></td></tr>
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
