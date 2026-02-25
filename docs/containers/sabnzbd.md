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
<tr><td><div id="tag26046" onclick="CopyToClipboard('tag26046');return false;" class="tag-decoration">nightly</div><div id="tag16060" onclick="CopyToClipboard('tag16060');return false;" class="tag-decoration">nightly-d119b9c</div><div id="tag10414" onclick="CopyToClipboard('tag10414');return false;" class="tag-decoration">nightly-e8791f9c7b188b50fac8a83ddd18ad1787a8248a</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d119b9c7a304fa8220e9bff73e62e568b54bd45d" target="_blank">Version update: 9b1b503ce6f2b70df39d2296aed4b7e296f2f18f => e8791f9c7b188b50fac8a83ddd18ad1787a8248a</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22299623228" target="_blank">2026-02-23 09:12:51</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag811" onclick="CopyToClipboard('tag811');return false;" class="tag-decoration">release</div><div id="tag22817" onclick="CopyToClipboard('tag22817');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag21931" onclick="CopyToClipboard('tag21931');return false;" class="tag-decoration">release-4.5.5</div><div id="tag2934" onclick="CopyToClipboard('tag2934');return false;" class="tag-decoration">release-v4</div><div id="tag28258" onclick="CopyToClipboard('tag28258');return false;" class="tag-decoration">release-v4.5</div><div id="tag29870" onclick="CopyToClipboard('tag29870');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag27894" onclick="CopyToClipboard('tag27894');return false;" class="tag-decoration">testing</div><div id="tag135" onclick="CopyToClipboard('tag135');return false;" class="tag-decoration">testing-3dc0cdf</div><div id="tag12073" onclick="CopyToClipboard('tag12073');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag5288" onclick="CopyToClipboard('tag5288');return false;" class="tag-decoration">testing-v4</div><div id="tag1375" onclick="CopyToClipboard('tag1375');return false;" class="tag-decoration">testing-v4.5</div><div id="tag24862" onclick="CopyToClipboard('tag24862');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3dc0cdf9be0128f86ab1d3137f11ee412fbc5fa6" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823273556" target="_blank">2026-02-09 11:29:12</a></td></tr>
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
