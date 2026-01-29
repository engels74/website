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
<tr><td><div id="tag658" onclick="CopyToClipboard('tag658');return false;" class="tag-decoration">nightly</div><div id="tag6703" onclick="CopyToClipboard('tag6703');return false;" class="tag-decoration">nightly-387fc94</div><div id="tag2454" onclick="CopyToClipboard('tag2454');return false;" class="tag-decoration">nightly-e2921e7b9c6b2c5a1cdf12f570e7c9cdbfb2aa50</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/387fc94a728c7baef7f77c1d17c35f19bbf9cae9" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469644784" target="_blank">2026-01-29 07:35:37</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag3221" onclick="CopyToClipboard('tag3221');return false;" class="tag-decoration">release</div><div id="tag26939" onclick="CopyToClipboard('tag26939');return false;" class="tag-decoration">release-2bf7455</div><div id="tag32393" onclick="CopyToClipboard('tag32393');return false;" class="tag-decoration">release-4.5.5</div><div id="tag26058" onclick="CopyToClipboard('tag26058');return false;" class="tag-decoration">release-v4</div><div id="tag29395" onclick="CopyToClipboard('tag29395');return false;" class="tag-decoration">release-v4.5</div><div id="tag7639" onclick="CopyToClipboard('tag7639');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2bf7455ca506aeb132cea7493e58ea81d09b301f" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645114" target="_blank">2026-01-29 07:35:38</a></td></tr>
<tr><td><div id="tag30431" onclick="CopyToClipboard('tag30431');return false;" class="tag-decoration">testing</div><div id="tag5426" onclick="CopyToClipboard('tag5426');return false;" class="tag-decoration">testing-045581e</div><div id="tag30741" onclick="CopyToClipboard('tag30741');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag8673" onclick="CopyToClipboard('tag8673');return false;" class="tag-decoration">testing-v4</div><div id="tag18159" onclick="CopyToClipboard('tag18159');return false;" class="tag-decoration">testing-v4.5</div><div id="tag28944" onclick="CopyToClipboard('tag28944');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/045581e27148697ee96df4505fa3abe854471819" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645621" target="_blank">2026-01-29 07:35:39</a></td></tr>
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
