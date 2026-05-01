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
<tr><td><div id="tag769" onclick="CopyToClipboard('tag769');return false;" class="tag-decoration">nightly</div><div id="tag15341" onclick="CopyToClipboard('tag15341');return false;" class="tag-decoration">nightly-712e85e</div><div id="tag13315" onclick="CopyToClipboard('tag13315');return false;" class="tag-decoration">nightly-51ea306d9ff60c6e665e2aeedf73de57413d7e98</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/712e85eeeba27c86429649bdda065a5a60e0e44f" target="_blank">Version update: 96975050b5c2526a4f81c8c06cb1ab9b18be6d17 => 51ea306d9ff60c6e665e2aeedf73de57413d7e98</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25173782279" target="_blank">2026-04-30 15:21:02</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag28457" onclick="CopyToClipboard('tag28457');return false;" class="tag-decoration">release</div><div id="tag24413" onclick="CopyToClipboard('tag24413');return false;" class="tag-decoration">release-7db252b</div><div id="tag31457" onclick="CopyToClipboard('tag31457');return false;" class="tag-decoration">release-4.5.5</div><div id="tag3547" onclick="CopyToClipboard('tag3547');return false;" class="tag-decoration">release-v4</div><div id="tag25124" onclick="CopyToClipboard('tag25124');return false;" class="tag-decoration">release-v4.5</div><div id="tag14223" onclick="CopyToClipboard('tag14223');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7db252bf08540717a7aa74602c9d639c04d3ad2e" target="_blank">Upstream update: alpinevpn-167fa4e => alpinevpn-4699fa7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24552121945" target="_blank">2026-04-17 06:53:48</a></td></tr>
<tr><td><div id="tag23920" onclick="CopyToClipboard('tag23920');return false;" class="tag-decoration">testing</div><div id="tag22644" onclick="CopyToClipboard('tag22644');return false;" class="tag-decoration">testing-b707f58</div><div id="tag21088" onclick="CopyToClipboard('tag21088');return false;" class="tag-decoration">testing-5.0.0</div><div id="tag30238" onclick="CopyToClipboard('tag30238');return false;" class="tag-decoration">testing-v5</div><div id="tag25125" onclick="CopyToClipboard('tag25125');return false;" class="tag-decoration">testing-v5.0</div><div id="tag21801" onclick="CopyToClipboard('tag21801');return false;" class="tag-decoration">testing-v5.0.0</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b707f5886a1d1d77d0cbaf119da322f894d7b232" target="_blank">Version update: 4.5.5 => 5.0.0</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25209435131" target="_blank">2026-05-01 09:20:41</a></td></tr>
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
