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
<tr><td><div id="tag15378" onclick="CopyToClipboard('tag15378');return false;" class="tag-decoration">nightly</div><div id="tag8174" onclick="CopyToClipboard('tag8174');return false;" class="tag-decoration">nightly-f5f36be</div><div id="tag22930" onclick="CopyToClipboard('tag22930');return false;" class="tag-decoration">nightly-0411e8acc150922cc6d11e22e0c51a6de7c64ff7</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f5f36becb31a76a9e8436df19aebf2341533a8fe" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395685812" target="_blank">2026-07-28 20:17:24</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag12553" onclick="CopyToClipboard('tag12553');return false;" class="tag-decoration">release</div><div id="tag19448" onclick="CopyToClipboard('tag19448');return false;" class="tag-decoration">release-5f790bd</div><div id="tag31981" onclick="CopyToClipboard('tag31981');return false;" class="tag-decoration">release-5.0.4</div><div id="tag13594" onclick="CopyToClipboard('tag13594');return false;" class="tag-decoration">release-v5</div><div id="tag15382" onclick="CopyToClipboard('tag15382');return false;" class="tag-decoration">release-v5.0</div><div id="tag30276" onclick="CopyToClipboard('tag30276');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f790bdb14f2be10d3bd4c9ab4b2c57e6ce00894" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395690614" target="_blank">2026-07-28 20:17:28</a></td></tr>
<tr><td><div id="tag28075" onclick="CopyToClipboard('tag28075');return false;" class="tag-decoration">testing</div><div id="tag26285" onclick="CopyToClipboard('tag26285');return false;" class="tag-decoration">testing-e9cd211</div><div id="tag32287" onclick="CopyToClipboard('tag32287');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag26387" onclick="CopyToClipboard('tag26387');return false;" class="tag-decoration">testing-v5</div><div id="tag30191" onclick="CopyToClipboard('tag30191');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23019" onclick="CopyToClipboard('tag23019');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e9cd2115d416d088e240ddbf9ffa1ca00028e41e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30379532293" target="_blank">2026-07-28 16:42:45</a></td></tr>
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
