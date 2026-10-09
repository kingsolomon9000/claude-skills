# claude-skills

Claude Code skills installed globally at the start of every cloud session.

`skills.txt` lists one `npx skills add` source per line. The cloud environment's
setup script reads it and installs each entry:

```bash
curl -fsSL https://raw.githubusercontent.com/kingsolomon9000/claude-skills/main/skills.txt | while read -r s; do
  [ -n "$s" ] && npx -y skills add $s -g -a claude-code -y < /dev/null || true
done
```

To add a skill, append a line to `skills.txt`.
