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
<tr><td><div id="tag3913" onclick="CopyToClipboard('tag3913');return false;" class="tag-decoration">nightly</div><div id="tag25104" onclick="CopyToClipboard('tag25104');return false;" class="tag-decoration">nightly-df1c0915d07982546e282b2b52354a49cde993ba</div><div id="tag24487" onclick="CopyToClipboard('tag24487');return false;" class="tag-decoration">nightly-f3a8e88</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f3a8e88ee3e3e9a1eed915d50b9a60c584bb2d41" target="_blank">Upstream update: alpinevpn-5251e5c => alpinevpn-337a82e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20858010138" target="_blank">2026-01-09 16:12:35</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag1700" onclick="CopyToClipboard('tag1700');return false;" class="tag-decoration">release</div><div id="tag22236" onclick="CopyToClipboard('tag22236');return false;" class="tag-decoration">release-4.5.5</div><div id="tag22478" onclick="CopyToClipboard('tag22478');return false;" class="tag-decoration">release-b01c151</div><div id="tag29069" onclick="CopyToClipboard('tag29069');return false;" class="tag-decoration">release-v4</div><div id="tag11637" onclick="CopyToClipboard('tag11637');return false;" class="tag-decoration">release-v4.5</div><div id="tag14188" onclick="CopyToClipboard('tag14188');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b01c1518a6f19b2601bd544dd6c4fdcc6b90f3b2" target="_blank">Upstream update: alpinevpn-5251e5c => alpinevpn-337a82e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20858010334" target="_blank">2026-01-09 16:12:37</a></td></tr>
<tr><td><div id="tag5458" onclick="CopyToClipboard('tag5458');return false;" class="tag-decoration">testing</div><div id="tag19657" onclick="CopyToClipboard('tag19657');return false;" class="tag-decoration">testing-4.6.0Beta2</div><div id="tag9790" onclick="CopyToClipboard('tag9790');return false;" class="tag-decoration">testing-e1609e2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e1609e219c5cad356876027595d1ad686d1441c2" target="_blank">Upstream update: alpinevpn-5251e5c => alpinevpn-337a82e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20858010922" target="_blank">2026-01-09 16:12:38</a></td></tr>
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
