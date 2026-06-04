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
<tr><td><div id="tag10426" onclick="CopyToClipboard('tag10426');return false;" class="tag-decoration">nightly</div><div id="tag13514" onclick="CopyToClipboard('tag13514');return false;" class="tag-decoration">nightly-61e7fbe</div><div id="tag21737" onclick="CopyToClipboard('tag21737');return false;" class="tag-decoration">nightly-5e3126cd141de8247c29e9f813380cf0a90d7ef9</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/61e7fbe3d2eb9a024ecd0625918277f87ebbb55f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26950272972" target="_blank">2026-06-04 11:58:15</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29617" onclick="CopyToClipboard('tag29617');return false;" class="tag-decoration">release</div><div id="tag17023" onclick="CopyToClipboard('tag17023');return false;" class="tag-decoration">release-bcf36ce</div><div id="tag20568" onclick="CopyToClipboard('tag20568');return false;" class="tag-decoration">release-5.0.3</div><div id="tag14936" onclick="CopyToClipboard('tag14936');return false;" class="tag-decoration">release-v5</div><div id="tag6939" onclick="CopyToClipboard('tag6939');return false;" class="tag-decoration">release-v5.0</div><div id="tag30721" onclick="CopyToClipboard('tag30721');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/bcf36cef7a746f9ef94e609755b9263b9a747688" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710781564" target="_blank">2026-05-31 11:01:09</a></td></tr>
<tr><td><div id="tag2171" onclick="CopyToClipboard('tag2171');return false;" class="tag-decoration">testing</div><div id="tag29620" onclick="CopyToClipboard('tag29620');return false;" class="tag-decoration">testing-009193c</div><div id="tag19612" onclick="CopyToClipboard('tag19612');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag25311" onclick="CopyToClipboard('tag25311');return false;" class="tag-decoration">testing-v5</div><div id="tag12597" onclick="CopyToClipboard('tag12597');return false;" class="tag-decoration">testing-v5.0</div><div id="tag18164" onclick="CopyToClipboard('tag18164');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/009193c9e6c31de8f8cdff399b7f16aa7f6beaaf" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710782493" target="_blank">2026-05-31 11:01:11</a></td></tr>
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
