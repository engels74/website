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
<tr><td><div id="tag25388" onclick="CopyToClipboard('tag25388');return false;" class="tag-decoration">nightly</div><div id="tag21984" onclick="CopyToClipboard('tag21984');return false;" class="tag-decoration">nightly-4770709</div><div id="tag24031" onclick="CopyToClipboard('tag24031');return false;" class="tag-decoration">nightly-aee1cd8e41853970f667a031ee19602df28f35c2</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/4770709e7b33b8f477c62b525a599e80227515f2" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27417010716" target="_blank">2026-06-12 12:55:39</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag30668" onclick="CopyToClipboard('tag30668');return false;" class="tag-decoration">release</div><div id="tag23015" onclick="CopyToClipboard('tag23015');return false;" class="tag-decoration">release-746e018</div><div id="tag21609" onclick="CopyToClipboard('tag21609');return false;" class="tag-decoration">release-5.0.4</div><div id="tag16875" onclick="CopyToClipboard('tag16875');return false;" class="tag-decoration">release-v5</div><div id="tag1098" onclick="CopyToClipboard('tag1098');return false;" class="tag-decoration">release-v5.0</div><div id="tag12271" onclick="CopyToClipboard('tag12271');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/746e018cd50910dae73acbd4ab2ae90183233d6c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354913378" target="_blank">2026-06-11 14:40:57</a></td></tr>
<tr><td><div id="tag11659" onclick="CopyToClipboard('tag11659');return false;" class="tag-decoration">testing</div><div id="tag10605" onclick="CopyToClipboard('tag10605');return false;" class="tag-decoration">testing-1b1942e</div><div id="tag22553" onclick="CopyToClipboard('tag22553');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag21740" onclick="CopyToClipboard('tag21740');return false;" class="tag-decoration">testing-v5</div><div id="tag4187" onclick="CopyToClipboard('tag4187');return false;" class="tag-decoration">testing-v5.0</div><div id="tag8856" onclick="CopyToClipboard('tag8856');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b1942e349033b72b39f15958dc0694493b2d37d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354916499" target="_blank">2026-06-11 14:40:59</a></td></tr>
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
