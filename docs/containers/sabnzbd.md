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
<tr><td><div id="tag22762" onclick="CopyToClipboard('tag22762');return false;" class="tag-decoration">nightly</div><div id="tag20458" onclick="CopyToClipboard('tag20458');return false;" class="tag-decoration">nightly-72608c7</div><div id="tag14455" onclick="CopyToClipboard('tag14455');return false;" class="tag-decoration">nightly-6d5901e953c0b5dc38f0d7ac8e5c5e75ec5e3a6b</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/72608c75fefcfc2c2c264fc74f59b1b37b4e9cd6" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33681176448" target="_blank">2026-09-02 20:45:25</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag28867" onclick="CopyToClipboard('tag28867');return false;" class="tag-decoration">release</div><div id="tag9087" onclick="CopyToClipboard('tag9087');return false;" class="tag-decoration">release-7db2161</div><div id="tag26219" onclick="CopyToClipboard('tag26219');return false;" class="tag-decoration">release-5.1.2</div><div id="tag6414" onclick="CopyToClipboard('tag6414');return false;" class="tag-decoration">release-v5</div><div id="tag32482" onclick="CopyToClipboard('tag32482');return false;" class="tag-decoration">release-v5.1</div><div id="tag9460" onclick="CopyToClipboard('tag9460');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7db21614c4a1f78e6d90902dba4267a54fadc2b9" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33609469740" target="_blank">2026-09-02 08:34:48</a></td></tr>
<tr><td><div id="tag1913" onclick="CopyToClipboard('tag1913');return false;" class="tag-decoration">testing</div><div id="tag21888" onclick="CopyToClipboard('tag21888');return false;" class="tag-decoration">testing-6cd4ab0</div><div id="tag22247" onclick="CopyToClipboard('tag22247');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag22126" onclick="CopyToClipboard('tag22126');return false;" class="tag-decoration">testing-v5</div><div id="tag24639" onclick="CopyToClipboard('tag24639');return false;" class="tag-decoration">testing-v5.1</div><div id="tag22250" onclick="CopyToClipboard('tag22250');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/6cd4ab06ee97a3a4cb1a49ccb9415949ecaceba6" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33609465257" target="_blank">2026-09-02 08:34:45</a></td></tr>
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
