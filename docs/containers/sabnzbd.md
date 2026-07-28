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
<tr><td><div id="tag20755" onclick="CopyToClipboard('tag20755');return false;" class="tag-decoration">nightly</div><div id="tag16196" onclick="CopyToClipboard('tag16196');return false;" class="tag-decoration">nightly-ecf9f94</div><div id="tag4666" onclick="CopyToClipboard('tag4666');return false;" class="tag-decoration">nightly-47a507f5a6be0780274db202663fc7f0c797aea2</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/ecf9f947f2765c66953dc0ce9eeb4390a38b736d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30379522335" target="_blank">2026-07-28 16:42:37</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15644" onclick="CopyToClipboard('tag15644');return false;" class="tag-decoration">release</div><div id="tag17642" onclick="CopyToClipboard('tag17642');return false;" class="tag-decoration">release-820753e</div><div id="tag10401" onclick="CopyToClipboard('tag10401');return false;" class="tag-decoration">release-5.0.4</div><div id="tag25929" onclick="CopyToClipboard('tag25929');return false;" class="tag-decoration">release-v5</div><div id="tag2420" onclick="CopyToClipboard('tag2420');return false;" class="tag-decoration">release-v5.0</div><div id="tag13243" onclick="CopyToClipboard('tag13243');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/820753e05837b36287e28fba09e19c63f35ae048" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30379518839" target="_blank">2026-07-28 16:42:35</a></td></tr>
<tr><td><div id="tag10548" onclick="CopyToClipboard('tag10548');return false;" class="tag-decoration">testing</div><div id="tag6135" onclick="CopyToClipboard('tag6135');return false;" class="tag-decoration">testing-e9cd211</div><div id="tag517" onclick="CopyToClipboard('tag517');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag2402" onclick="CopyToClipboard('tag2402');return false;" class="tag-decoration">testing-v5</div><div id="tag22031" onclick="CopyToClipboard('tag22031');return false;" class="tag-decoration">testing-v5.0</div><div id="tag21976" onclick="CopyToClipboard('tag21976');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e9cd2115d416d088e240ddbf9ffa1ca00028e41e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30379532293" target="_blank">2026-07-28 16:42:45</a></td></tr>
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
