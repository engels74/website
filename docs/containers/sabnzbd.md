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
<tr><td><div id="tag20641" onclick="CopyToClipboard('tag20641');return false;" class="tag-decoration">nightly</div><div id="tag17015" onclick="CopyToClipboard('tag17015');return false;" class="tag-decoration">nightly-0b3afd6</div><div id="tag17110" onclick="CopyToClipboard('tag17110');return false;" class="tag-decoration">nightly-df1c0915d07982546e282b2b52354a49cde993ba</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/0b3afd69e339493d6a4317ca0594e98f2a0da1e2" target="_blank">Upstream update: alpinevpn-213d573 => alpinevpn-89f692c</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20935303421" target="_blank">2026-01-12 21:17:26</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag17042" onclick="CopyToClipboard('tag17042');return false;" class="tag-decoration">release</div><div id="tag27451" onclick="CopyToClipboard('tag27451');return false;" class="tag-decoration">release-19d5e3b</div><div id="tag18958" onclick="CopyToClipboard('tag18958');return false;" class="tag-decoration">release-4.5.5</div><div id="tag17949" onclick="CopyToClipboard('tag17949');return false;" class="tag-decoration">release-v4</div><div id="tag19504" onclick="CopyToClipboard('tag19504');return false;" class="tag-decoration">release-v4.5</div><div id="tag18983" onclick="CopyToClipboard('tag18983');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/19d5e3b33f6357a309a4173ae5113de0a345bcd4" target="_blank">Upstream update: alpinevpn-89f692c => alpinevpn-dc8231b</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20936843653" target="_blank">2026-01-12 22:13:47</a></td></tr>
<tr><td><div id="tag30071" onclick="CopyToClipboard('tag30071');return false;" class="tag-decoration">testing</div><div id="tag16537" onclick="CopyToClipboard('tag16537');return false;" class="tag-decoration">testing-e37971e</div><div id="tag23580" onclick="CopyToClipboard('tag23580');return false;" class="tag-decoration">testing-4.6.0Beta2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e37971e7f21d0341cf2ee8db3332c8f796a5d44c" target="_blank">Upstream update: alpinevpn-89f692c => alpinevpn-dc8231b</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20936844090" target="_blank">2026-01-12 22:13:48</a></td></tr>
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
