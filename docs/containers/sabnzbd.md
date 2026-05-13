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
<tr><td><div id="tag29334" onclick="CopyToClipboard('tag29334');return false;" class="tag-decoration">nightly</div><div id="tag20892" onclick="CopyToClipboard('tag20892');return false;" class="tag-decoration">nightly-2224b64</div><div id="tag32046" onclick="CopyToClipboard('tag32046');return false;" class="tag-decoration">nightly-2184964d7877e0fddee0fd0421e6c21fd38ceae7</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/2224b64459b836904957b998bae3583d3eb6cb8f" target="_blank">Version update: b942e06297ab039a6ff848d5e479ec374ab907f2 => 2184964d7877e0fddee0fd0421e6c21fd38ceae7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25816491843" target="_blank">2026-05-13 17:49:01</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15133" onclick="CopyToClipboard('tag15133');return false;" class="tag-decoration">release</div><div id="tag16214" onclick="CopyToClipboard('tag16214');return false;" class="tag-decoration">release-649b812</div><div id="tag26452" onclick="CopyToClipboard('tag26452');return false;" class="tag-decoration">release-5.0.1</div><div id="tag11490" onclick="CopyToClipboard('tag11490');return false;" class="tag-decoration">release-v5</div><div id="tag12299" onclick="CopyToClipboard('tag12299');return false;" class="tag-decoration">release-v5.0</div><div id="tag26193" onclick="CopyToClipboard('tag26193');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/649b812ac39bc1438fd036c57634649a269e6095" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25720796668" target="_blank">2026-05-12 07:45:03</a></td></tr>
<tr><td><div id="tag5289" onclick="CopyToClipboard('tag5289');return false;" class="tag-decoration">testing</div><div id="tag26764" onclick="CopyToClipboard('tag26764');return false;" class="tag-decoration">testing-f1c91ab</div><div id="tag10302" onclick="CopyToClipboard('tag10302');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag21399" onclick="CopyToClipboard('tag21399');return false;" class="tag-decoration">testing-v5</div><div id="tag13596" onclick="CopyToClipboard('tag13596');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23571" onclick="CopyToClipboard('tag23571');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f1c91ab1227b24e3a2a1950ddcc065e4b7e1a1ef" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25720803851" target="_blank">2026-05-12 07:45:11</a></td></tr>
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
