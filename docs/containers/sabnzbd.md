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
<tr><td><div id="tag5120" onclick="CopyToClipboard('tag5120');return false;" class="tag-decoration">nightly</div><div id="tag16995" onclick="CopyToClipboard('tag16995');return false;" class="tag-decoration">nightly-598a2a6</div><div id="tag19175" onclick="CopyToClipboard('tag19175');return false;" class="tag-decoration">nightly-dbe7cb336d9f09ba4e782fb88854a7cfa8a59563</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/598a2a6471d1bc5d2db1f9188657364486456ff4" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28391311289" target="_blank">2026-06-29 17:40:51</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag28571" onclick="CopyToClipboard('tag28571');return false;" class="tag-decoration">release</div><div id="tag19495" onclick="CopyToClipboard('tag19495');return false;" class="tag-decoration">release-7dcae8e</div><div id="tag16206" onclick="CopyToClipboard('tag16206');return false;" class="tag-decoration">release-5.0.4</div><div id="tag20411" onclick="CopyToClipboard('tag20411');return false;" class="tag-decoration">release-v5</div><div id="tag23901" onclick="CopyToClipboard('tag23901');return false;" class="tag-decoration">release-v5.0</div><div id="tag28372" onclick="CopyToClipboard('tag28372');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7dcae8eaa21d3fc246cf22dcb5abe05713efd24a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27987238337" target="_blank">2026-06-22 22:06:19</a></td></tr>
<tr><td><div id="tag11609" onclick="CopyToClipboard('tag11609');return false;" class="tag-decoration">testing</div><div id="tag7931" onclick="CopyToClipboard('tag7931');return false;" class="tag-decoration">testing-0afca37</div><div id="tag27877" onclick="CopyToClipboard('tag27877');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag32260" onclick="CopyToClipboard('tag32260');return false;" class="tag-decoration">testing-v5</div><div id="tag11012" onclick="CopyToClipboard('tag11012');return false;" class="tag-decoration">testing-v5.0</div><div id="tag12620" onclick="CopyToClipboard('tag12620');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/0afca379eb53eabd2b0061d2c89351357c56d806" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27987238526" target="_blank">2026-06-22 22:06:20</a></td></tr>
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
