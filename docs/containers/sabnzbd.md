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
<tr><td><div id="tag24304" onclick="CopyToClipboard('tag24304');return false;" class="tag-decoration">nightly</div><div id="tag23306" onclick="CopyToClipboard('tag23306');return false;" class="tag-decoration">nightly-058a52b</div><div id="tag3728" onclick="CopyToClipboard('tag3728');return false;" class="tag-decoration">nightly-a4de70496713ea705ee275b3c75df1b499b90dbb</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/058a52b33681e5d336bf2f623772e0845e1362b9" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21389829077" target="_blank">2026-01-27 08:23:31</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag10091" onclick="CopyToClipboard('tag10091');return false;" class="tag-decoration">release</div><div id="tag21805" onclick="CopyToClipboard('tag21805');return false;" class="tag-decoration">release-fe2b475</div><div id="tag6058" onclick="CopyToClipboard('tag6058');return false;" class="tag-decoration">release-4.5.5</div><div id="tag29392" onclick="CopyToClipboard('tag29392');return false;" class="tag-decoration">release-v4</div><div id="tag23453" onclick="CopyToClipboard('tag23453');return false;" class="tag-decoration">release-v4.5</div><div id="tag22837" onclick="CopyToClipboard('tag22837');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/fe2b475ca1dfab2e96ed4e5a1d8eaa7dfe822c8b" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21389829582" target="_blank">2026-01-27 08:23:32</a></td></tr>
<tr><td><div id="tag18784" onclick="CopyToClipboard('tag18784');return false;" class="tag-decoration">testing</div><div id="tag19743" onclick="CopyToClipboard('tag19743');return false;" class="tag-decoration">testing-0570f77</div><div id="tag7746" onclick="CopyToClipboard('tag7746');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag12591" onclick="CopyToClipboard('tag12591');return false;" class="tag-decoration">testing-v4</div><div id="tag16149" onclick="CopyToClipboard('tag16149');return false;" class="tag-decoration">testing-v4.5</div><div id="tag28418" onclick="CopyToClipboard('tag28418');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/0570f77391285ec4a93a027d57253635e4b45084" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21389830108" target="_blank">2026-01-27 08:23:33</a></td></tr>
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
