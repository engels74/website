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
<tr><td><div id="tag19605" onclick="CopyToClipboard('tag19605');return false;" class="tag-decoration">nightly</div><div id="tag26448" onclick="CopyToClipboard('tag26448');return false;" class="tag-decoration">nightly-448e933</div><div id="tag7761" onclick="CopyToClipboard('tag7761');return false;" class="tag-decoration">nightly-ec6ba3baaeb721e765037846fac780719671c86e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/448e9336a8ff64a4bbbc14de71236991e654751e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31411496916" target="_blank">2026-08-10 16:56:02</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20720" onclick="CopyToClipboard('tag20720');return false;" class="tag-decoration">release</div><div id="tag1341" onclick="CopyToClipboard('tag1341');return false;" class="tag-decoration">release-4f52fdc</div><div id="tag8525" onclick="CopyToClipboard('tag8525');return false;" class="tag-decoration">release-5.1.0</div><div id="tag21928" onclick="CopyToClipboard('tag21928');return false;" class="tag-decoration">release-v5</div><div id="tag10548" onclick="CopyToClipboard('tag10548');return false;" class="tag-decoration">release-v5.1</div><div id="tag12643" onclick="CopyToClipboard('tag12643');return false;" class="tag-decoration">release-v5.1.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4f52fdc0a42c22190fc463595a5b999d3bbdac23" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31385230026" target="_blank">2026-08-10 11:49:48</a></td></tr>
<tr><td><div id="tag13135" onclick="CopyToClipboard('tag13135');return false;" class="tag-decoration">testing</div><div id="tag17371" onclick="CopyToClipboard('tag17371');return false;" class="tag-decoration">testing-8a563c6</div><div id="tag25311" onclick="CopyToClipboard('tag25311');return false;" class="tag-decoration">testing-5.1.0</div><div id="tag23618" onclick="CopyToClipboard('tag23618');return false;" class="tag-decoration">testing-v5</div><div id="tag4397" onclick="CopyToClipboard('tag4397');return false;" class="tag-decoration">testing-v5.1</div><div id="tag21941" onclick="CopyToClipboard('tag21941');return false;" class="tag-decoration">testing-v5.1.0</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8a563c6b41a6e1f23e25a80be0466fc62b3048b9" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31385222689" target="_blank">2026-08-10 11:49:42</a></td></tr>
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
