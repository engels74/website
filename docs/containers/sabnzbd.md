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
<tr><td><div id="tag30288" onclick="CopyToClipboard('tag30288');return false;" class="tag-decoration">nightly</div><div id="tag14827" onclick="CopyToClipboard('tag14827');return false;" class="tag-decoration">nightly-7eeac98</div><div id="tag26378" onclick="CopyToClipboard('tag26378');return false;" class="tag-decoration">nightly-6cbe811d105cd9ef9485bf6ce965ce52d785e621</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7eeac98c26a21aa3ee36dbdda0ec4dc637a5a42e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33854422086" target="_blank">2026-09-04 08:38:31</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag12579" onclick="CopyToClipboard('tag12579');return false;" class="tag-decoration">release</div><div id="tag31733" onclick="CopyToClipboard('tag31733');return false;" class="tag-decoration">release-5da462e</div><div id="tag29459" onclick="CopyToClipboard('tag29459');return false;" class="tag-decoration">release-5.1.2</div><div id="tag2593" onclick="CopyToClipboard('tag2593');return false;" class="tag-decoration">release-v5</div><div id="tag13321" onclick="CopyToClipboard('tag13321');return false;" class="tag-decoration">release-v5.1</div><div id="tag1231" onclick="CopyToClipboard('tag1231');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5da462ec75174d481f861cdd3b553e78d3f6237c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33803892915" target="_blank">2026-09-03 20:43:08</a></td></tr>
<tr><td><div id="tag18344" onclick="CopyToClipboard('tag18344');return false;" class="tag-decoration">testing</div><div id="tag19072" onclick="CopyToClipboard('tag19072');return false;" class="tag-decoration">testing-b9cc709</div><div id="tag26472" onclick="CopyToClipboard('tag26472');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag7200" onclick="CopyToClipboard('tag7200');return false;" class="tag-decoration">testing-v5</div><div id="tag16368" onclick="CopyToClipboard('tag16368');return false;" class="tag-decoration">testing-v5.1</div><div id="tag3116" onclick="CopyToClipboard('tag3116');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b9cc709a37cfdcbf2531266baac2c22025a935f7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33803889022" target="_blank">2026-09-03 20:43:06</a></td></tr>
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
