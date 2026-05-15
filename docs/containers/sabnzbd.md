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
<tr><td><div id="tag23842" onclick="CopyToClipboard('tag23842');return false;" class="tag-decoration">nightly</div><div id="tag11731" onclick="CopyToClipboard('tag11731');return false;" class="tag-decoration">nightly-c37ab04</div><div id="tag18636" onclick="CopyToClipboard('tag18636');return false;" class="tag-decoration">nightly-b6b992e521defbf4c7ed043de316c90f6fb7f36e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c37ab04c62b492b056282930b31a34d5179ca273" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25917599125" target="_blank">2026-05-15 12:24:11</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29786" onclick="CopyToClipboard('tag29786');return false;" class="tag-decoration">release</div><div id="tag8394" onclick="CopyToClipboard('tag8394');return false;" class="tag-decoration">release-7516841</div><div id="tag27169" onclick="CopyToClipboard('tag27169');return false;" class="tag-decoration">release-5.0.2</div><div id="tag11919" onclick="CopyToClipboard('tag11919');return false;" class="tag-decoration">release-v5</div><div id="tag7854" onclick="CopyToClipboard('tag7854');return false;" class="tag-decoration">release-v5.0</div><div id="tag28746" onclick="CopyToClipboard('tag28746');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/751684146b169926751579982a97f34f05e07550" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25916727735" target="_blank">2026-05-15 12:02:08</a></td></tr>
<tr><td><div id="tag18293" onclick="CopyToClipboard('tag18293');return false;" class="tag-decoration">testing</div><div id="tag27883" onclick="CopyToClipboard('tag27883');return false;" class="tag-decoration">testing-1c665da</div><div id="tag16502" onclick="CopyToClipboard('tag16502');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag10203" onclick="CopyToClipboard('tag10203');return false;" class="tag-decoration">testing-v5</div><div id="tag23282" onclick="CopyToClipboard('tag23282');return false;" class="tag-decoration">testing-v5.0</div><div id="tag9803" onclick="CopyToClipboard('tag9803');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1c665da53b1d0c73113bc5856abd1bf597a1cf75" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25916729044" target="_blank">2026-05-15 12:02:10</a></td></tr>
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
