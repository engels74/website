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
<tr><td><div id="tag21525" onclick="CopyToClipboard('tag21525');return false;" class="tag-decoration">nightly</div><div id="tag4675" onclick="CopyToClipboard('tag4675');return false;" class="tag-decoration">nightly-7427f2f</div><div id="tag26077" onclick="CopyToClipboard('tag26077');return false;" class="tag-decoration">nightly-ef2ee17c135c313e12c74455a0472edbae711e79</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7427f2fdc72f5e1698ebda7c184d5baa36d93b6e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29243187711" target="_blank">2026-07-13 10:33:49</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag32521" onclick="CopyToClipboard('tag32521');return false;" class="tag-decoration">release</div><div id="tag6851" onclick="CopyToClipboard('tag6851');return false;" class="tag-decoration">release-030e780</div><div id="tag13123" onclick="CopyToClipboard('tag13123');return false;" class="tag-decoration">release-5.0.4</div><div id="tag8837" onclick="CopyToClipboard('tag8837');return false;" class="tag-decoration">release-v5</div><div id="tag28394" onclick="CopyToClipboard('tag28394');return false;" class="tag-decoration">release-v5.0</div><div id="tag20907" onclick="CopyToClipboard('tag20907');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/030e78057bbc0c34f6721d253dcb34e78a1e2e57" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29308895282" target="_blank">2026-07-14 05:34:34</a></td></tr>
<tr><td><div id="tag9302" onclick="CopyToClipboard('tag9302');return false;" class="tag-decoration">testing</div><div id="tag680" onclick="CopyToClipboard('tag680');return false;" class="tag-decoration">testing-5fd6272</div><div id="tag26688" onclick="CopyToClipboard('tag26688');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag4326" onclick="CopyToClipboard('tag4326');return false;" class="tag-decoration">testing-v5</div><div id="tag3711" onclick="CopyToClipboard('tag3711');return false;" class="tag-decoration">testing-v5.0</div><div id="tag11808" onclick="CopyToClipboard('tag11808');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5fd627228d81b49e236e2a338d01d89f99664375" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979412430" target="_blank">2026-07-08 22:13:27</a></td></tr>
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
