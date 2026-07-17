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
<tr><td><div id="tag3377" onclick="CopyToClipboard('tag3377');return false;" class="tag-decoration">nightly</div><div id="tag2223" onclick="CopyToClipboard('tag2223');return false;" class="tag-decoration">nightly-fd0c35b</div><div id="tag3756" onclick="CopyToClipboard('tag3756');return false;" class="tag-decoration">nightly-6731da2d68aee212fc717b72abefc6832271dfda</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/fd0c35b51997f0aaee1b35286bdf8a736d92a241" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29579404024" target="_blank">2026-07-17 12:12:02</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26714" onclick="CopyToClipboard('tag26714');return false;" class="tag-decoration">release</div><div id="tag29259" onclick="CopyToClipboard('tag29259');return false;" class="tag-decoration">release-e4d88ea</div><div id="tag12501" onclick="CopyToClipboard('tag12501');return false;" class="tag-decoration">release-5.0.4</div><div id="tag7160" onclick="CopyToClipboard('tag7160');return false;" class="tag-decoration">release-v5</div><div id="tag2211" onclick="CopyToClipboard('tag2211');return false;" class="tag-decoration">release-v5.0</div><div id="tag4365" onclick="CopyToClipboard('tag4365');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e4d88eaa0bfa608eb5869477cfa6f834660b119e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29489996210" target="_blank">2026-07-16 10:12:26</a></td></tr>
<tr><td><div id="tag5069" onclick="CopyToClipboard('tag5069');return false;" class="tag-decoration">testing</div><div id="tag10653" onclick="CopyToClipboard('tag10653');return false;" class="tag-decoration">testing-7336589</div><div id="tag30313" onclick="CopyToClipboard('tag30313');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag19779" onclick="CopyToClipboard('tag19779');return false;" class="tag-decoration">testing-v5</div><div id="tag12181" onclick="CopyToClipboard('tag12181');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23430" onclick="CopyToClipboard('tag23430');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7336589951f67b55cde564e1a07a1e94d19f0c6e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29489995661" target="_blank">2026-07-16 10:12:24</a></td></tr>
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
