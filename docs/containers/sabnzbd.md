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
<tr><td><div id="tag16576" onclick="CopyToClipboard('tag16576');return false;" class="tag-decoration">nightly</div><div id="tag12406" onclick="CopyToClipboard('tag12406');return false;" class="tag-decoration">nightly-aa6c4b4</div><div id="tag12249" onclick="CopyToClipboard('tag12249');return false;" class="tag-decoration">nightly-395f8dc4c5c8163e3c641576436eb4987d464fe0</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/aa6c4b4ba1bd94bf899aa56cb0b5f10bbd631d16" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552119975" target="_blank">2026-04-17 06:53:45</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag18574" onclick="CopyToClipboard('tag18574');return false;" class="tag-decoration">release</div><div id="tag18653" onclick="CopyToClipboard('tag18653');return false;" class="tag-decoration">release-7db252b</div><div id="tag21924" onclick="CopyToClipboard('tag21924');return false;" class="tag-decoration">release-4.5.5</div><div id="tag18030" onclick="CopyToClipboard('tag18030');return false;" class="tag-decoration">release-v4</div><div id="tag3629" onclick="CopyToClipboard('tag3629');return false;" class="tag-decoration">release-v4.5</div><div id="tag1407" onclick="CopyToClipboard('tag1407');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7db252bf08540717a7aa74602c9d639c04d3ad2e" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552121945" target="_blank">2026-04-17 06:53:48</a></td></tr>
<tr><td><div id="tag26978" onclick="CopyToClipboard('tag26978');return false;" class="tag-decoration">testing</div><div id="tag19389" onclick="CopyToClipboard('tag19389');return false;" class="tag-decoration">testing-7cfcbd6</div><div id="tag6185" onclick="CopyToClipboard('tag6185');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag5937" onclick="CopyToClipboard('tag5937');return false;" class="tag-decoration">testing-v4</div><div id="tag17936" onclick="CopyToClipboard('tag17936');return false;" class="tag-decoration">testing-v4.5</div><div id="tag13187" onclick="CopyToClipboard('tag13187');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7cfcbd6176ce3f990aee507d9ef2284ac757746b" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552122310" target="_blank">2026-04-17 06:53:49</a></td></tr>
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
