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
<tr><td><div id="tag13566" onclick="CopyToClipboard('tag13566');return false;" class="tag-decoration">nightly</div><div id="tag31704" onclick="CopyToClipboard('tag31704');return false;" class="tag-decoration">nightly-47fc5e2</div><div id="tag24340" onclick="CopyToClipboard('tag24340');return false;" class="tag-decoration">nightly-cc61dc974b383e5bce04746274407448b6d0443e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/47fc5e273497c433b8de9bfe8b22982b9513c589" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26680261829" target="_blank">2026-05-30 09:21:23</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag22984" onclick="CopyToClipboard('tag22984');return false;" class="tag-decoration">release</div><div id="tag22659" onclick="CopyToClipboard('tag22659');return false;" class="tag-decoration">release-57fc17b</div><div id="tag31453" onclick="CopyToClipboard('tag31453');return false;" class="tag-decoration">release-5.0.3</div><div id="tag8039" onclick="CopyToClipboard('tag8039');return false;" class="tag-decoration">release-v5</div><div id="tag32163" onclick="CopyToClipboard('tag32163');return false;" class="tag-decoration">release-v5.0</div><div id="tag25135" onclick="CopyToClipboard('tag25135');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/57fc17b33e7834ded4db8f07e036160ab28d1aa7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26527215739" target="_blank">2026-05-27 17:22:26</a></td></tr>
<tr><td><div id="tag29156" onclick="CopyToClipboard('tag29156');return false;" class="tag-decoration">testing</div><div id="tag10133" onclick="CopyToClipboard('tag10133');return false;" class="tag-decoration">testing-3113535</div><div id="tag2113" onclick="CopyToClipboard('tag2113');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag19754" onclick="CopyToClipboard('tag19754');return false;" class="tag-decoration">testing-v5</div><div id="tag16813" onclick="CopyToClipboard('tag16813');return false;" class="tag-decoration">testing-v5.0</div><div id="tag2240" onclick="CopyToClipboard('tag2240');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3113535654387f51b90f4257027b910bb44c2b1d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26527218596" target="_blank">2026-05-27 17:22:28</a></td></tr>
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
