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
<tr><td><div id="tag9833" onclick="CopyToClipboard('tag9833');return false;" class="tag-decoration">nightly</div><div id="tag3562" onclick="CopyToClipboard('tag3562');return false;" class="tag-decoration">nightly-aec6019</div><div id="tag25758" onclick="CopyToClipboard('tag25758');return false;" class="tag-decoration">nightly-507edc3ddf81669380843fd25003780539644d98</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/aec60193694346763399fa8a4729ea590dced683" target="_blank">Version update: 920e23e11e51b0ff19de511cbba398b7d89d3b15 => 507edc3ddf81669380843fd25003780539644d98</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21818077233" target="_blank">2026-02-09 08:41:19</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag24169" onclick="CopyToClipboard('tag24169');return false;" class="tag-decoration">release</div><div id="tag21400" onclick="CopyToClipboard('tag21400');return false;" class="tag-decoration">release-252442e</div><div id="tag28528" onclick="CopyToClipboard('tag28528');return false;" class="tag-decoration">release-4.5.5</div><div id="tag18251" onclick="CopyToClipboard('tag18251');return false;" class="tag-decoration">release-v4</div><div id="tag12954" onclick="CopyToClipboard('tag12954');return false;" class="tag-decoration">release-v4.5</div><div id="tag22002" onclick="CopyToClipboard('tag22002');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/252442ee081e7bffb07db68d74238fe65fe61492" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823272944" target="_blank">2026-02-09 11:29:10</a></td></tr>
<tr><td><div id="tag8082" onclick="CopyToClipboard('tag8082');return false;" class="tag-decoration">testing</div><div id="tag27348" onclick="CopyToClipboard('tag27348');return false;" class="tag-decoration">testing-045581e</div><div id="tag9081" onclick="CopyToClipboard('tag9081');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag19873" onclick="CopyToClipboard('tag19873');return false;" class="tag-decoration">testing-v4</div><div id="tag25795" onclick="CopyToClipboard('tag25795');return false;" class="tag-decoration">testing-v4.5</div><div id="tag30645" onclick="CopyToClipboard('tag30645');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/045581e27148697ee96df4505fa3abe854471819" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645621" target="_blank">2026-01-29 07:35:39</a></td></tr>
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
