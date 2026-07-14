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
<tr><td><div id="tag23722" onclick="CopyToClipboard('tag23722');return false;" class="tag-decoration">nightly</div><div id="tag24495" onclick="CopyToClipboard('tag24495');return false;" class="tag-decoration">nightly-42bdde7</div><div id="tag12907" onclick="CopyToClipboard('tag12907');return false;" class="tag-decoration">nightly-ef2ee17c135c313e12c74455a0472edbae711e79</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/42bdde7c0582affb6c8fa0ddbcc2386e5e91b14a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29308898172" target="_blank">2026-07-14 05:34:37</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag11754" onclick="CopyToClipboard('tag11754');return false;" class="tag-decoration">release</div><div id="tag9640" onclick="CopyToClipboard('tag9640');return false;" class="tag-decoration">release-030e780</div><div id="tag1569" onclick="CopyToClipboard('tag1569');return false;" class="tag-decoration">release-5.0.4</div><div id="tag27243" onclick="CopyToClipboard('tag27243');return false;" class="tag-decoration">release-v5</div><div id="tag14502" onclick="CopyToClipboard('tag14502');return false;" class="tag-decoration">release-v5.0</div><div id="tag2331" onclick="CopyToClipboard('tag2331');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/030e78057bbc0c34f6721d253dcb34e78a1e2e57" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29308895282" target="_blank">2026-07-14 05:34:34</a></td></tr>
<tr><td><div id="tag27950" onclick="CopyToClipboard('tag27950');return false;" class="tag-decoration">testing</div><div id="tag10665" onclick="CopyToClipboard('tag10665');return false;" class="tag-decoration">testing-432fb34</div><div id="tag9806" onclick="CopyToClipboard('tag9806');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag7053" onclick="CopyToClipboard('tag7053');return false;" class="tag-decoration">testing-v5</div><div id="tag31828" onclick="CopyToClipboard('tag31828');return false;" class="tag-decoration">testing-v5.0</div><div id="tag479" onclick="CopyToClipboard('tag479');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/432fb3421b5a0e248fe2d8f59656461649108a28" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29308897588" target="_blank">2026-07-14 05:34:37</a></td></tr>
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
