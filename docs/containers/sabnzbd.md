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
<tr><td><div id="tag8687" onclick="CopyToClipboard('tag8687');return false;" class="tag-decoration">nightly</div><div id="tag31755" onclick="CopyToClipboard('tag31755');return false;" class="tag-decoration">nightly-1dd5eb1</div><div id="tag6674" onclick="CopyToClipboard('tag6674');return false;" class="tag-decoration">nightly-96975050b5c2526a4f81c8c06cb1ab9b18be6d17</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/1dd5eb1440f6c59f00cb68c8b16c4d1661040b70" target="_blank">Version update: b84fd1526aeb4526be0498f90e52bf92922812c3 => 96975050b5c2526a4f81c8c06cb1ab9b18be6d17</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25159320532" target="_blank">2026-04-30 09:59:42</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag11856" onclick="CopyToClipboard('tag11856');return false;" class="tag-decoration">release</div><div id="tag9752" onclick="CopyToClipboard('tag9752');return false;" class="tag-decoration">release-7db252b</div><div id="tag2088" onclick="CopyToClipboard('tag2088');return false;" class="tag-decoration">release-4.5.5</div><div id="tag3132" onclick="CopyToClipboard('tag3132');return false;" class="tag-decoration">release-v4</div><div id="tag14303" onclick="CopyToClipboard('tag14303');return false;" class="tag-decoration">release-v4.5</div><div id="tag14256" onclick="CopyToClipboard('tag14256');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7db252bf08540717a7aa74602c9d639c04d3ad2e" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552121945" target="_blank">2026-04-17 06:53:48</a></td></tr>
<tr><td><div id="tag15540" onclick="CopyToClipboard('tag15540');return false;" class="tag-decoration">testing</div><div id="tag25962" onclick="CopyToClipboard('tag25962');return false;" class="tag-decoration">testing-7cfcbd6</div><div id="tag28338" onclick="CopyToClipboard('tag28338');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag21730" onclick="CopyToClipboard('tag21730');return false;" class="tag-decoration">testing-v4</div><div id="tag22151" onclick="CopyToClipboard('tag22151');return false;" class="tag-decoration">testing-v4.5</div><div id="tag11830" onclick="CopyToClipboard('tag11830');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7cfcbd6176ce3f990aee507d9ef2284ac757746b" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552122310" target="_blank">2026-04-17 06:53:49</a></td></tr>
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
