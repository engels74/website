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
<tr><td><div id="tag30674" onclick="CopyToClipboard('tag30674');return false;" class="tag-decoration">nightly</div><div id="tag18852" onclick="CopyToClipboard('tag18852');return false;" class="tag-decoration">nightly-c2c3626</div><div id="tag28241" onclick="CopyToClipboard('tag28241');return false;" class="tag-decoration">nightly-d48a2f89c645f8972ece0cd608c21be4a4b964dd</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c2c3626638af96b31bf6fe4bbaef1f295704a81d" target="_blank">Version update: d8e572f0915f2f62385e6d780cf9b91a569e7d42 => d48a2f89c645f8972ece0cd608c21be4a4b964dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25286607314" target="_blank">2026-05-03 18:01:19</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag4826" onclick="CopyToClipboard('tag4826');return false;" class="tag-decoration">release</div><div id="tag27665" onclick="CopyToClipboard('tag27665');return false;" class="tag-decoration">release-8d79706</div><div id="tag28911" onclick="CopyToClipboard('tag28911');return false;" class="tag-decoration">release-5.0.1</div><div id="tag1910" onclick="CopyToClipboard('tag1910');return false;" class="tag-decoration">release-v5</div><div id="tag6434" onclick="CopyToClipboard('tag6434');return false;" class="tag-decoration">release-v5.0</div><div id="tag32328" onclick="CopyToClipboard('tag32328');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8d7970682214e86f4df593db68c24b605a1a5718" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254172" target="_blank">2026-05-01 21:37:08</a></td></tr>
<tr><td><div id="tag23665" onclick="CopyToClipboard('tag23665');return false;" class="tag-decoration">testing</div><div id="tag7189" onclick="CopyToClipboard('tag7189');return false;" class="tag-decoration">testing-2b55556</div><div id="tag26000" onclick="CopyToClipboard('tag26000');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag18691" onclick="CopyToClipboard('tag18691');return false;" class="tag-decoration">testing-v5</div><div id="tag29934" onclick="CopyToClipboard('tag29934');return false;" class="tag-decoration">testing-v5.0</div><div id="tag773" onclick="CopyToClipboard('tag773');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b5555662f7d34c27829058643eff45c1b6eee87" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254956" target="_blank">2026-05-01 21:37:10</a></td></tr>
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
