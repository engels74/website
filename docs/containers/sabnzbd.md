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
<tr><td><div id="tag22762" onclick="CopyToClipboard('tag22762');return false;" class="tag-decoration">nightly</div><div id="tag5871" onclick="CopyToClipboard('tag5871');return false;" class="tag-decoration">nightly-f9b4c26</div><div id="tag9260" onclick="CopyToClipboard('tag9260');return false;" class="tag-decoration">nightly-8bc81bc4ce3c3cbcca6a263a5122bff49c1c0b12</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f9b4c26a2fcb9e4b97efe72b35e5d807cff480d9" target="_blank">Version update: aa87657552f9546a5cf2f0500d13cfac2ece2f00 => 8bc81bc4ce3c3cbcca6a263a5122bff49c1c0b12</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22049668316" target="_blank">2026-02-16 04:02:24</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag5704" onclick="CopyToClipboard('tag5704');return false;" class="tag-decoration">release</div><div id="tag27196" onclick="CopyToClipboard('tag27196');return false;" class="tag-decoration">release-252442e</div><div id="tag18619" onclick="CopyToClipboard('tag18619');return false;" class="tag-decoration">release-4.5.5</div><div id="tag10730" onclick="CopyToClipboard('tag10730');return false;" class="tag-decoration">release-v4</div><div id="tag25742" onclick="CopyToClipboard('tag25742');return false;" class="tag-decoration">release-v4.5</div><div id="tag13654" onclick="CopyToClipboard('tag13654');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/252442ee081e7bffb07db68d74238fe65fe61492" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823272944" target="_blank">2026-02-09 11:29:10</a></td></tr>
<tr><td><div id="tag423" onclick="CopyToClipboard('tag423');return false;" class="tag-decoration">testing</div><div id="tag23490" onclick="CopyToClipboard('tag23490');return false;" class="tag-decoration">testing-3dc0cdf</div><div id="tag26832" onclick="CopyToClipboard('tag26832');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag28869" onclick="CopyToClipboard('tag28869');return false;" class="tag-decoration">testing-v4</div><div id="tag3963" onclick="CopyToClipboard('tag3963');return false;" class="tag-decoration">testing-v4.5</div><div id="tag22016" onclick="CopyToClipboard('tag22016');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3dc0cdf9be0128f86ab1d3137f11ee412fbc5fa6" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823273556" target="_blank">2026-02-09 11:29:12</a></td></tr>
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
