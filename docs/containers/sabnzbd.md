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
<tr><td><div id="tag11830" onclick="CopyToClipboard('tag11830');return false;" class="tag-decoration">nightly</div><div id="tag21628" onclick="CopyToClipboard('tag21628');return false;" class="tag-decoration">nightly-e5fe7a9</div><div id="tag30930" onclick="CopyToClipboard('tag30930');return false;" class="tag-decoration">nightly-d25d857fc4c6d1d7c7bf9fffb718074d50cda325</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e5fe7a98d42317b3986c509b76492389142b67fa" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33947114437" target="_blank">2026-09-05 05:24:17</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag3731" onclick="CopyToClipboard('tag3731');return false;" class="tag-decoration">release</div><div id="tag8715" onclick="CopyToClipboard('tag8715');return false;" class="tag-decoration">release-8bd143f</div><div id="tag9222" onclick="CopyToClipboard('tag9222');return false;" class="tag-decoration">release-5.1.2</div><div id="tag29971" onclick="CopyToClipboard('tag29971');return false;" class="tag-decoration">release-v5</div><div id="tag25639" onclick="CopyToClipboard('tag25639');return false;" class="tag-decoration">release-v5.1</div><div id="tag13380" onclick="CopyToClipboard('tag13380');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8bd143fb6d25403239baa9f0548a7f96f75b6d1a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33916524632" target="_blank">2026-09-04 20:30:00</a></td></tr>
<tr><td><div id="tag13020" onclick="CopyToClipboard('tag13020');return false;" class="tag-decoration">testing</div><div id="tag11370" onclick="CopyToClipboard('tag11370');return false;" class="tag-decoration">testing-2a1223c</div><div id="tag19411" onclick="CopyToClipboard('tag19411');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag4532" onclick="CopyToClipboard('tag4532');return false;" class="tag-decoration">testing-v5</div><div id="tag11838" onclick="CopyToClipboard('tag11838');return false;" class="tag-decoration">testing-v5.1</div><div id="tag25888" onclick="CopyToClipboard('tag25888');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2a1223cbcb89b0795d40299cbd8efd5e4549fa8f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33916522917" target="_blank">2026-09-04 20:29:59</a></td></tr>
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
