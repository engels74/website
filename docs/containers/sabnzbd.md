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
<tr><td><div id="tag4812" onclick="CopyToClipboard('tag4812');return false;" class="tag-decoration">nightly</div><div id="tag26448" onclick="CopyToClipboard('tag26448');return false;" class="tag-decoration">nightly-97d63cb</div><div id="tag7641" onclick="CopyToClipboard('tag7641');return false;" class="tag-decoration">nightly-e1cd1eed83c6f877ef27586f5cebf13448c07794</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/97d63cb3bfb717b62f8d077e811170325283ba00" target="_blank">Upstream update: alpinevpn-fe778dd => alpinevpn-a8c5f31</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21426195779" target="_blank">2026-01-28 05:22:48</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag4912" onclick="CopyToClipboard('tag4912');return false;" class="tag-decoration">release</div><div id="tag27192" onclick="CopyToClipboard('tag27192');return false;" class="tag-decoration">release-fe2b475</div><div id="tag2408" onclick="CopyToClipboard('tag2408');return false;" class="tag-decoration">release-4.5.5</div><div id="tag1433" onclick="CopyToClipboard('tag1433');return false;" class="tag-decoration">release-v4</div><div id="tag29825" onclick="CopyToClipboard('tag29825');return false;" class="tag-decoration">release-v4.5</div><div id="tag9050" onclick="CopyToClipboard('tag9050');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/fe2b475ca1dfab2e96ed4e5a1d8eaa7dfe822c8b" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21389829582" target="_blank">2026-01-27 08:23:32</a></td></tr>
<tr><td><div id="tag18530" onclick="CopyToClipboard('tag18530');return false;" class="tag-decoration">testing</div><div id="tag11096" onclick="CopyToClipboard('tag11096');return false;" class="tag-decoration">testing-0570f77</div><div id="tag4589" onclick="CopyToClipboard('tag4589');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag4901" onclick="CopyToClipboard('tag4901');return false;" class="tag-decoration">testing-v4</div><div id="tag3132" onclick="CopyToClipboard('tag3132');return false;" class="tag-decoration">testing-v4.5</div><div id="tag15103" onclick="CopyToClipboard('tag15103');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/0570f77391285ec4a93a027d57253635e4b45084" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21389830108" target="_blank">2026-01-27 08:23:33</a></td></tr>
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
