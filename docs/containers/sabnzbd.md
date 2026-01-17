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
<tr><td><div id="tag23436" onclick="CopyToClipboard('tag23436');return false;" class="tag-decoration">nightly</div><div id="tag13390" onclick="CopyToClipboard('tag13390');return false;" class="tag-decoration">nightly-6b76cb9</div><div id="tag14654" onclick="CopyToClipboard('tag14654');return false;" class="tag-decoration">nightly-df1c0915d07982546e282b2b52354a49cde993ba</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/6b76cb9c516991268f36eb9d12e88e59a229a596" target="_blank">Upstream update: alpinevpn-c74319d => alpinevpn-0a5023e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21097248300" target="_blank">2026-01-17 16:15:25</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag1387" onclick="CopyToClipboard('tag1387');return false;" class="tag-decoration">release</div><div id="tag9908" onclick="CopyToClipboard('tag9908');return false;" class="tag-decoration">release-1b3137f</div><div id="tag1355" onclick="CopyToClipboard('tag1355');return false;" class="tag-decoration">release-4.5.5</div><div id="tag11334" onclick="CopyToClipboard('tag11334');return false;" class="tag-decoration">release-v4</div><div id="tag14914" onclick="CopyToClipboard('tag14914');return false;" class="tag-decoration">release-v4.5</div><div id="tag14071" onclick="CopyToClipboard('tag14071');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b3137fb6fa6a24b66fbb6e414ded10e059fbb35" target="_blank">Upstream update: alpinevpn-897a0b9 => alpinevpn-c74319d</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21074856285" target="_blank">2026-01-16 17:19:30</a></td></tr>
<tr><td><div id="tag15172" onclick="CopyToClipboard('tag15172');return false;" class="tag-decoration">testing</div><div id="tag5077" onclick="CopyToClipboard('tag5077');return false;" class="tag-decoration">testing-a6a492d</div><div id="tag31415" onclick="CopyToClipboard('tag31415');return false;" class="tag-decoration">testing-4.6.0Beta2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/a6a492d4c54c82e29d88e34d1bf78564225e08dc" target="_blank">Upstream update: alpinevpn-c74319d => alpinevpn-0a5023e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21097248580" target="_blank">2026-01-17 16:15:27</a></td></tr>
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
