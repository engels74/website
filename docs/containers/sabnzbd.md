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
<tr><td><div id="tag28985" onclick="CopyToClipboard('tag28985');return false;" class="tag-decoration">nightly</div><div id="tag15764" onclick="CopyToClipboard('tag15764');return false;" class="tag-decoration">nightly-634395a</div><div id="tag11177" onclick="CopyToClipboard('tag11177');return false;" class="tag-decoration">nightly-45aafe07744f12852e3731bd99e9f72064c47998</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/634395af73ad8ab9887f697c5f0214d23e19a3a3" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27235613756" target="_blank">2026-06-09 21:01:50</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag3042" onclick="CopyToClipboard('tag3042');return false;" class="tag-decoration">release</div><div id="tag21300" onclick="CopyToClipboard('tag21300');return false;" class="tag-decoration">release-54d73ad</div><div id="tag32653" onclick="CopyToClipboard('tag32653');return false;" class="tag-decoration">release-5.0.3</div><div id="tag9678" onclick="CopyToClipboard('tag9678');return false;" class="tag-decoration">release-v5</div><div id="tag18010" onclick="CopyToClipboard('tag18010');return false;" class="tag-decoration">release-v5.0</div><div id="tag32668" onclick="CopyToClipboard('tag32668');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/54d73addb8fc3a44795e8c69778aba56b83e6c9a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27276007223" target="_blank">2026-06-10 12:24:22</a></td></tr>
<tr><td><div id="tag18109" onclick="CopyToClipboard('tag18109');return false;" class="tag-decoration">testing</div><div id="tag9239" onclick="CopyToClipboard('tag9239');return false;" class="tag-decoration">testing-009193c</div><div id="tag4547" onclick="CopyToClipboard('tag4547');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag23502" onclick="CopyToClipboard('tag23502');return false;" class="tag-decoration">testing-v5</div><div id="tag4052" onclick="CopyToClipboard('tag4052');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23769" onclick="CopyToClipboard('tag23769');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/009193c9e6c31de8f8cdff399b7f16aa7f6beaaf" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710782493" target="_blank">2026-05-31 11:01:11</a></td></tr>
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
