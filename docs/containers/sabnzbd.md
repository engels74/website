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
<tr><td><div id="tag21320" onclick="CopyToClipboard('tag21320');return false;" class="tag-decoration">nightly</div><div id="tag29391" onclick="CopyToClipboard('tag29391');return false;" class="tag-decoration">nightly-6b76cb9</div><div id="tag4400" onclick="CopyToClipboard('tag4400');return false;" class="tag-decoration">nightly-df1c0915d07982546e282b2b52354a49cde993ba</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/6b76cb9c516991268f36eb9d12e88e59a229a596" target="_blank">Upstream update: alpinevpn-c74319d => alpinevpn-0a5023e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21097248300" target="_blank">2026-01-17 16:15:25</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15814" onclick="CopyToClipboard('tag15814');return false;" class="tag-decoration">release</div><div id="tag387" onclick="CopyToClipboard('tag387');return false;" class="tag-decoration">release-f490352</div><div id="tag10176" onclick="CopyToClipboard('tag10176');return false;" class="tag-decoration">release-4.5.5</div><div id="tag27476" onclick="CopyToClipboard('tag27476');return false;" class="tag-decoration">release-v4</div><div id="tag4858" onclick="CopyToClipboard('tag4858');return false;" class="tag-decoration">release-v4.5</div><div id="tag24149" onclick="CopyToClipboard('tag24149');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f4903525dd73e570bbe09fd1db8e899257fcd14b" target="_blank">Upstream update: alpinevpn-c74319d => alpinevpn-0a5023e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21097248427" target="_blank">2026-01-17 16:15:26</a></td></tr>
<tr><td><div id="tag27098" onclick="CopyToClipboard('tag27098');return false;" class="tag-decoration">testing</div><div id="tag22345" onclick="CopyToClipboard('tag22345');return false;" class="tag-decoration">testing-a6a492d</div><div id="tag5360" onclick="CopyToClipboard('tag5360');return false;" class="tag-decoration">testing-4.6.0Beta2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/a6a492d4c54c82e29d88e34d1bf78564225e08dc" target="_blank">Upstream update: alpinevpn-c74319d => alpinevpn-0a5023e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21097248580" target="_blank">2026-01-17 16:15:27</a></td></tr>
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
