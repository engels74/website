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
<tr><td><div id="tag5706" onclick="CopyToClipboard('tag5706');return false;" class="tag-decoration">nightly</div><div id="tag4041" onclick="CopyToClipboard('tag4041');return false;" class="tag-decoration">nightly-3263536</div><div id="tag12598" onclick="CopyToClipboard('tag12598');return false;" class="tag-decoration">nightly-80840ce74356c0875b0701b5768f0789315fffa8</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/3263536c767c50d104ee452b65b28340585afb65" target="_blank">ci: point at engels74/base-image@workflows</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25881620015" target="_blank">2026-05-14 19:43:19</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16253" onclick="CopyToClipboard('tag16253');return false;" class="tag-decoration">release</div><div id="tag13061" onclick="CopyToClipboard('tag13061');return false;" class="tag-decoration">release-8cf5da7</div><div id="tag15485" onclick="CopyToClipboard('tag15485');return false;" class="tag-decoration">release-5.0.2</div><div id="tag16255" onclick="CopyToClipboard('tag16255');return false;" class="tag-decoration">release-v5</div><div id="tag14553" onclick="CopyToClipboard('tag14553');return false;" class="tag-decoration">release-v5.0</div><div id="tag13838" onclick="CopyToClipboard('tag13838');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8cf5da726675a249f35840f39e57d601dde6ca98" target="_blank">ci: point at engels74/base-image@workflows</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25881622029" target="_blank">2026-05-14 19:43:21</a></td></tr>
<tr><td><div id="tag3945" onclick="CopyToClipboard('tag3945');return false;" class="tag-decoration">testing</div><div id="tag25523" onclick="CopyToClipboard('tag25523');return false;" class="tag-decoration">testing-1c665da</div><div id="tag18003" onclick="CopyToClipboard('tag18003');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag18063" onclick="CopyToClipboard('tag18063');return false;" class="tag-decoration">testing-v5</div><div id="tag27047" onclick="CopyToClipboard('tag27047');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23393" onclick="CopyToClipboard('tag23393');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1c665da53b1d0c73113bc5856abd1bf597a1cf75" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25916729044" target="_blank">2026-05-15 12:02:10</a></td></tr>
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
