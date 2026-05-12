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
<tr><td><div id="tag2150" onclick="CopyToClipboard('tag2150');return false;" class="tag-decoration">nightly</div><div id="tag20957" onclick="CopyToClipboard('tag20957');return false;" class="tag-decoration">nightly-73dbc9b</div><div id="tag9585" onclick="CopyToClipboard('tag9585');return false;" class="tag-decoration">nightly-90798e5e4dcbd2e45bc0aa36f95de482e08b8cea</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/73dbc9ba68de78a492b53af47e7054f3a6697655" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25720790824" target="_blank">2026-05-12 07:44:55</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag31643" onclick="CopyToClipboard('tag31643');return false;" class="tag-decoration">release</div><div id="tag18070" onclick="CopyToClipboard('tag18070');return false;" class="tag-decoration">release-4860033</div><div id="tag3143" onclick="CopyToClipboard('tag3143');return false;" class="tag-decoration">release-5.0.1</div><div id="tag10255" onclick="CopyToClipboard('tag10255');return false;" class="tag-decoration">release-v5</div><div id="tag20375" onclick="CopyToClipboard('tag20375');return false;" class="tag-decoration">release-v5.0</div><div id="tag11662" onclick="CopyToClipboard('tag11662');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4860033077730c63ff750af32c2e02fc3ce04fa9" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25713910671" target="_blank">2026-05-12 04:44:38</a></td></tr>
<tr><td><div id="tag30198" onclick="CopyToClipboard('tag30198');return false;" class="tag-decoration">testing</div><div id="tag15729" onclick="CopyToClipboard('tag15729');return false;" class="tag-decoration">testing-f1c91ab</div><div id="tag22133" onclick="CopyToClipboard('tag22133');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag8502" onclick="CopyToClipboard('tag8502');return false;" class="tag-decoration">testing-v5</div><div id="tag24220" onclick="CopyToClipboard('tag24220');return false;" class="tag-decoration">testing-v5.0</div><div id="tag16854" onclick="CopyToClipboard('tag16854');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f1c91ab1227b24e3a2a1950ddcc065e4b7e1a1ef" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25720803851" target="_blank">2026-05-12 07:45:11</a></td></tr>
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
