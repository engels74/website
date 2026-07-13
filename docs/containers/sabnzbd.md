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
<tr><td><div id="tag18737" onclick="CopyToClipboard('tag18737');return false;" class="tag-decoration">nightly</div><div id="tag16079" onclick="CopyToClipboard('tag16079');return false;" class="tag-decoration">nightly-7427f2f</div><div id="tag11908" onclick="CopyToClipboard('tag11908');return false;" class="tag-decoration">nightly-ef2ee17c135c313e12c74455a0472edbae711e79</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7427f2fdc72f5e1698ebda7c184d5baa36d93b6e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29243187711" target="_blank">2026-07-13 10:33:49</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag24239" onclick="CopyToClipboard('tag24239');return false;" class="tag-decoration">release</div><div id="tag18027" onclick="CopyToClipboard('tag18027');return false;" class="tag-decoration">release-aa1692b</div><div id="tag12751" onclick="CopyToClipboard('tag12751');return false;" class="tag-decoration">release-5.0.4</div><div id="tag12563" onclick="CopyToClipboard('tag12563');return false;" class="tag-decoration">release-v5</div><div id="tag27755" onclick="CopyToClipboard('tag27755');return false;" class="tag-decoration">release-v5.0</div><div id="tag5644" onclick="CopyToClipboard('tag5644');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aa1692b699b5339ee61eccad93ca9f3459641ddd" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979413673" target="_blank">2026-07-08 22:13:28</a></td></tr>
<tr><td><div id="tag728" onclick="CopyToClipboard('tag728');return false;" class="tag-decoration">testing</div><div id="tag29589" onclick="CopyToClipboard('tag29589');return false;" class="tag-decoration">testing-5fd6272</div><div id="tag2452" onclick="CopyToClipboard('tag2452');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag12634" onclick="CopyToClipboard('tag12634');return false;" class="tag-decoration">testing-v5</div><div id="tag16524" onclick="CopyToClipboard('tag16524');return false;" class="tag-decoration">testing-v5.0</div><div id="tag22464" onclick="CopyToClipboard('tag22464');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5fd627228d81b49e236e2a338d01d89f99664375" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979412430" target="_blank">2026-07-08 22:13:27</a></td></tr>
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
