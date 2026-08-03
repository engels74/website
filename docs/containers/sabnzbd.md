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
<tr><td><div id="tag1293" onclick="CopyToClipboard('tag1293');return false;" class="tag-decoration">nightly</div><div id="tag24124" onclick="CopyToClipboard('tag24124');return false;" class="tag-decoration">nightly-c745825</div><div id="tag21207" onclick="CopyToClipboard('tag21207');return false;" class="tag-decoration">nightly-70f89e98e8a38301fe8acb6e63b768550f2faab9</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c74582578065350f71a2d711f737963a0eba6a8a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30828942283" target="_blank">2026-08-03 15:44:49</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag18595" onclick="CopyToClipboard('tag18595');return false;" class="tag-decoration">release</div><div id="tag1043" onclick="CopyToClipboard('tag1043');return false;" class="tag-decoration">release-5f790bd</div><div id="tag898" onclick="CopyToClipboard('tag898');return false;" class="tag-decoration">release-5.0.4</div><div id="tag9609" onclick="CopyToClipboard('tag9609');return false;" class="tag-decoration">release-v5</div><div id="tag10799" onclick="CopyToClipboard('tag10799');return false;" class="tag-decoration">release-v5.0</div><div id="tag15324" onclick="CopyToClipboard('tag15324');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f790bdb14f2be10d3bd4c9ab4b2c57e6ce00894" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395690614" target="_blank">2026-07-28 20:17:28</a></td></tr>
<tr><td><div id="tag7366" onclick="CopyToClipboard('tag7366');return false;" class="tag-decoration">testing</div><div id="tag17335" onclick="CopyToClipboard('tag17335');return false;" class="tag-decoration">testing-94ee6c5</div><div id="tag4879" onclick="CopyToClipboard('tag4879');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag2586" onclick="CopyToClipboard('tag2586');return false;" class="tag-decoration">testing-v5</div><div id="tag2287" onclick="CopyToClipboard('tag2287');return false;" class="tag-decoration">testing-v5.0</div><div id="tag26816" onclick="CopyToClipboard('tag26816');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/94ee6c563c8c0c85251526fc0ac61909d43225d7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395681904" target="_blank">2026-07-28 20:17:20</a></td></tr>
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
