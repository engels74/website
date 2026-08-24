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
<tr><td><div id="tag868" onclick="CopyToClipboard('tag868');return false;" class="tag-decoration">nightly</div><div id="tag15015" onclick="CopyToClipboard('tag15015');return false;" class="tag-decoration">nightly-41478e0</div><div id="tag22195" onclick="CopyToClipboard('tag22195');return false;" class="tag-decoration">nightly-0fe92487b62f6550874e5a1adfb4711046594d1c</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/41478e0ecee4f599f98f0b5c4b5b2c1765b4d906" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32694369631" target="_blank">2026-08-24 05:40:24</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29016" onclick="CopyToClipboard('tag29016');return false;" class="tag-decoration">release</div><div id="tag28921" onclick="CopyToClipboard('tag28921');return false;" class="tag-decoration">release-87f6728</div><div id="tag7757" onclick="CopyToClipboard('tag7757');return false;" class="tag-decoration">release-5.1.1</div><div id="tag32225" onclick="CopyToClipboard('tag32225');return false;" class="tag-decoration">release-v5</div><div id="tag16470" onclick="CopyToClipboard('tag16470');return false;" class="tag-decoration">release-v5.1</div><div id="tag28634" onclick="CopyToClipboard('tag28634');return false;" class="tag-decoration">release-v5.1.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/87f6728be54de4685822ca23f362b10fc05add0c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381402735" target="_blank">2026-08-20 14:38:57</a></td></tr>
<tr><td><div id="tag31336" onclick="CopyToClipboard('tag31336');return false;" class="tag-decoration">testing</div><div id="tag27926" onclick="CopyToClipboard('tag27926');return false;" class="tag-decoration">testing-e417274</div><div id="tag17191" onclick="CopyToClipboard('tag17191');return false;" class="tag-decoration">testing-5.1.1</div><div id="tag27565" onclick="CopyToClipboard('tag27565');return false;" class="tag-decoration">testing-v5</div><div id="tag22778" onclick="CopyToClipboard('tag22778');return false;" class="tag-decoration">testing-v5.1</div><div id="tag10204" onclick="CopyToClipboard('tag10204');return false;" class="tag-decoration">testing-v5.1.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e417274da1817bfeeeadbb99d597f90b9d06a636" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381393649" target="_blank">2026-08-20 14:38:53</a></td></tr>
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
