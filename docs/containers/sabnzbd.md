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
<tr><td><div id="tag10705" onclick="CopyToClipboard('tag10705');return false;" class="tag-decoration">nightly</div><div id="tag18575" onclick="CopyToClipboard('tag18575');return false;" class="tag-decoration">nightly-715e21e</div><div id="tag10916" onclick="CopyToClipboard('tag10916');return false;" class="tag-decoration">nightly-ee8d9bdcf94e9faf857fdfb5654ca0026ed51617</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/715e21e6f3b437d03eb432150a5c9e7d687bbca4" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28544573974" target="_blank">2026-07-01 20:07:30</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag27985" onclick="CopyToClipboard('tag27985');return false;" class="tag-decoration">release</div><div id="tag3977" onclick="CopyToClipboard('tag3977');return false;" class="tag-decoration">release-b30cf3c</div><div id="tag26864" onclick="CopyToClipboard('tag26864');return false;" class="tag-decoration">release-5.0.4</div><div id="tag13247" onclick="CopyToClipboard('tag13247');return false;" class="tag-decoration">release-v5</div><div id="tag8178" onclick="CopyToClipboard('tag8178');return false;" class="tag-decoration">release-v5.0</div><div id="tag30815" onclick="CopyToClipboard('tag30815');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b30cf3c8436673dc4b51fa0315c11553e8c8fac3" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28443343553" target="_blank">2026-06-30 12:12:17</a></td></tr>
<tr><td><div id="tag11536" onclick="CopyToClipboard('tag11536');return false;" class="tag-decoration">testing</div><div id="tag11029" onclick="CopyToClipboard('tag11029');return false;" class="tag-decoration">testing-870b377</div><div id="tag1192" onclick="CopyToClipboard('tag1192');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag16368" onclick="CopyToClipboard('tag16368');return false;" class="tag-decoration">testing-v5</div><div id="tag15494" onclick="CopyToClipboard('tag15494');return false;" class="tag-decoration">testing-v5.0</div><div id="tag18106" onclick="CopyToClipboard('tag18106');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/870b377c1295fdbbf529f0a4b1273c6b13c6f2ba" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28443343320" target="_blank">2026-06-30 12:12:17</a></td></tr>
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
