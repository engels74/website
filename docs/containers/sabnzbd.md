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
<tr><td><div id="tag23514" onclick="CopyToClipboard('tag23514');return false;" class="tag-decoration">nightly</div><div id="tag26342" onclick="CopyToClipboard('tag26342');return false;" class="tag-decoration">nightly-c68f9bd</div><div id="tag20365" onclick="CopyToClipboard('tag20365');return false;" class="tag-decoration">nightly-a8751c5e77cea4753d139bd785eef05ad99d22f0</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c68f9bd3012d27cf775dc8fafb98a9ce91dbeb73" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26192430951" target="_blank">2026-05-20 21:59:15</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag23388" onclick="CopyToClipboard('tag23388');return false;" class="tag-decoration">release</div><div id="tag5438" onclick="CopyToClipboard('tag5438');return false;" class="tag-decoration">release-5151550</div><div id="tag19162" onclick="CopyToClipboard('tag19162');return false;" class="tag-decoration">release-5.0.3</div><div id="tag7520" onclick="CopyToClipboard('tag7520');return false;" class="tag-decoration">release-v5</div><div id="tag2992" onclick="CopyToClipboard('tag2992');return false;" class="tag-decoration">release-v5.0</div><div id="tag10" onclick="CopyToClipboard('tag10');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5151550479f178f84b7e3deeb61850d5f803323e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26192425184" target="_blank">2026-05-20 21:59:08</a></td></tr>
<tr><td><div id="tag2544" onclick="CopyToClipboard('tag2544');return false;" class="tag-decoration">testing</div><div id="tag28768" onclick="CopyToClipboard('tag28768');return false;" class="tag-decoration">testing-f041b27</div><div id="tag9076" onclick="CopyToClipboard('tag9076');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag13942" onclick="CopyToClipboard('tag13942');return false;" class="tag-decoration">testing-v5</div><div id="tag21442" onclick="CopyToClipboard('tag21442');return false;" class="tag-decoration">testing-v5.0</div><div id="tag10676" onclick="CopyToClipboard('tag10676');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f041b2734542c20216152192dfedffc9bda8523b" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26192426649" target="_blank">2026-05-20 21:59:09</a></td></tr>
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
