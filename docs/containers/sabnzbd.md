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
<tr><td><div id="tag29157" onclick="CopyToClipboard('tag29157');return false;" class="tag-decoration">nightly</div><div id="tag11610" onclick="CopyToClipboard('tag11610');return false;" class="tag-decoration">nightly-59dd0ef</div><div id="tag10838" onclick="CopyToClipboard('tag10838');return false;" class="tag-decoration">nightly-f259e47110d4c510540ca50a26c67bf20b1b09c9</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/59dd0ef967e73839d5d3a9baea55d56a3e8df2e3" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25919010700" target="_blank">2026-05-15 12:57:01</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag12856" onclick="CopyToClipboard('tag12856');return false;" class="tag-decoration">release</div><div id="tag29366" onclick="CopyToClipboard('tag29366');return false;" class="tag-decoration">release-7516841</div><div id="tag25725" onclick="CopyToClipboard('tag25725');return false;" class="tag-decoration">release-5.0.2</div><div id="tag9551" onclick="CopyToClipboard('tag9551');return false;" class="tag-decoration">release-v5</div><div id="tag14042" onclick="CopyToClipboard('tag14042');return false;" class="tag-decoration">release-v5.0</div><div id="tag26851" onclick="CopyToClipboard('tag26851');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/751684146b169926751579982a97f34f05e07550" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25916727735" target="_blank">2026-05-15 12:02:08</a></td></tr>
<tr><td><div id="tag15674" onclick="CopyToClipboard('tag15674');return false;" class="tag-decoration">testing</div><div id="tag12429" onclick="CopyToClipboard('tag12429');return false;" class="tag-decoration">testing-1c665da</div><div id="tag15888" onclick="CopyToClipboard('tag15888');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag18535" onclick="CopyToClipboard('tag18535');return false;" class="tag-decoration">testing-v5</div><div id="tag26465" onclick="CopyToClipboard('tag26465');return false;" class="tag-decoration">testing-v5.0</div><div id="tag2678" onclick="CopyToClipboard('tag2678');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1c665da53b1d0c73113bc5856abd1bf597a1cf75" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25916729044" target="_blank">2026-05-15 12:02:10</a></td></tr>
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
