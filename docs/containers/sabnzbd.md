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
<tr><td><div id="tag16010" onclick="CopyToClipboard('tag16010');return false;" class="tag-decoration">nightly</div><div id="tag19586" onclick="CopyToClipboard('tag19586');return false;" class="tag-decoration">nightly-387fc94</div><div id="tag4153" onclick="CopyToClipboard('tag4153');return false;" class="tag-decoration">nightly-e2921e7b9c6b2c5a1cdf12f570e7c9cdbfb2aa50</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/387fc94a728c7baef7f77c1d17c35f19bbf9cae9" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469644784" target="_blank">2026-01-29 07:35:37</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26375" onclick="CopyToClipboard('tag26375');return false;" class="tag-decoration">release</div><div id="tag22309" onclick="CopyToClipboard('tag22309');return false;" class="tag-decoration">release-7a3cbbb</div><div id="tag1734" onclick="CopyToClipboard('tag1734');return false;" class="tag-decoration">release-4.5.5</div><div id="tag21419" onclick="CopyToClipboard('tag21419');return false;" class="tag-decoration">release-v4</div><div id="tag17754" onclick="CopyToClipboard('tag17754');return false;" class="tag-decoration">release-v4.5</div><div id="tag14420" onclick="CopyToClipboard('tag14420');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7a3cbbbfd02aa87893bbe849082ec0cf7dff832a" target="_blank">Upstream update: alpinevpn-fe778dd => alpinevpn-a8c5f31</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21426196175" target="_blank">2026-01-28 05:22:50</a></td></tr>
<tr><td><div id="tag11195" onclick="CopyToClipboard('tag11195');return false;" class="tag-decoration">testing</div><div id="tag14331" onclick="CopyToClipboard('tag14331');return false;" class="tag-decoration">testing-045581e</div><div id="tag1260" onclick="CopyToClipboard('tag1260');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag16605" onclick="CopyToClipboard('tag16605');return false;" class="tag-decoration">testing-v4</div><div id="tag18461" onclick="CopyToClipboard('tag18461');return false;" class="tag-decoration">testing-v4.5</div><div id="tag15046" onclick="CopyToClipboard('tag15046');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/045581e27148697ee96df4505fa3abe854471819" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645621" target="_blank">2026-01-29 07:35:39</a></td></tr>
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
