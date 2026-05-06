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
<tr><td><div id="tag18056" onclick="CopyToClipboard('tag18056');return false;" class="tag-decoration">nightly</div><div id="tag22917" onclick="CopyToClipboard('tag22917');return false;" class="tag-decoration">nightly-42d78a2</div><div id="tag8593" onclick="CopyToClipboard('tag8593');return false;" class="tag-decoration">nightly-ae170c68791945c73a28c56907afd52e2204795d</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/42d78a23c0ed7d8473c07ddfc3c6a9885b2d9e77" target="_blank">Version update: fc214a7ef9932246eebbc62575976a3d0e460473 => ae170c68791945c73a28c56907afd52e2204795d</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25437411783" target="_blank">2026-05-06 13:12:33</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag290" onclick="CopyToClipboard('tag290');return false;" class="tag-decoration">release</div><div id="tag32610" onclick="CopyToClipboard('tag32610');return false;" class="tag-decoration">release-8d79706</div><div id="tag6725" onclick="CopyToClipboard('tag6725');return false;" class="tag-decoration">release-5.0.1</div><div id="tag27569" onclick="CopyToClipboard('tag27569');return false;" class="tag-decoration">release-v5</div><div id="tag10934" onclick="CopyToClipboard('tag10934');return false;" class="tag-decoration">release-v5.0</div><div id="tag18226" onclick="CopyToClipboard('tag18226');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8d7970682214e86f4df593db68c24b605a1a5718" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254172" target="_blank">2026-05-01 21:37:08</a></td></tr>
<tr><td><div id="tag20512" onclick="CopyToClipboard('tag20512');return false;" class="tag-decoration">testing</div><div id="tag15565" onclick="CopyToClipboard('tag15565');return false;" class="tag-decoration">testing-2b55556</div><div id="tag1358" onclick="CopyToClipboard('tag1358');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag25552" onclick="CopyToClipboard('tag25552');return false;" class="tag-decoration">testing-v5</div><div id="tag17603" onclick="CopyToClipboard('tag17603');return false;" class="tag-decoration">testing-v5.0</div><div id="tag25822" onclick="CopyToClipboard('tag25822');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b5555662f7d34c27829058643eff45c1b6eee87" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254956" target="_blank">2026-05-01 21:37:10</a></td></tr>
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
