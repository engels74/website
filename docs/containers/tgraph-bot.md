---
hide:
  - toc
title: engels74/tgraph-bot
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/tgraph-bot){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/tgraph-bot){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Source Code](https://github.com/engels74/tgraph-bot-source){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/tgraph-bot.svg" alt="logo"></div>

!!! question "What is this?"

    This is a Docker image for my [tgraph-bot](https://github.com/engels74/tgraph-bot-source). It posts Tautulli graphs to a Discord channel of your choice, with many more features.

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
<tr><td><div id="tag15225" onclick="CopyToClipboard('tag15225');return false;" class="tag-decoration">nightly</div><div id="tag1772" onclick="CopyToClipboard('tag1772');return false;" class="tag-decoration">nightly-5e0c78c</div><div id="tag14252" onclick="CopyToClipboard('tag14252');return false;" class="tag-decoration">nightly-87784dd6255bbf3da172777d78608a038965a542</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/tgraph-bot/commit/5e0c78c6a6fc640244e09e1520cee5f4cfae616a" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/tgraph-bot/actions/runs/25713917739" target="_blank">2026-05-12 04:44:51</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name tgraph-bot \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        ghcr.io/engels74/tgraph-bot
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      tgraph-bot:
        container_name: tgraph-bot
        image: ghcr.io/engels74/tgraph-bot
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
        volumes:
          - /<host_folder_config>:/config
    ```

--8<-- "includes/wireguard.md"
