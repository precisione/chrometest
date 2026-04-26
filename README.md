# SOLO PER TEST

## LID (Linked Device ID) Support

Baileys now includes improved support for LID addressing to make bots more fluid and responsive. The library automatically handles:

- **LID/PN Addressing**: Automatic detection and routing to phone numbers or linked device IDs
- **Participant Mapping**: Proper mapping of participants with LID and PN contexts
- **Context Preservation**: LID information is preserved in message contexts for accurate responses

## Button Messages

Baileys now supports sending interactive button messages. There are two types of button messages:

### ButtonsMessage (Quick Reply Buttons)

```typescript
await sock.sendMessage(jid, {
  buttonsMessage: {
    text: 'Choose an option',
    footer: 'Footer text',
    buttons: [
      { displayText: 'Option 1', id: 'opt1' },
      { displayText: 'Option 2', id: 'opt2' }
    ]
  }
})
```

### TemplateMessage (CTA URL and Call Buttons)

```typescript
await sock.sendMessage(jid, {
  templateMessage: {
    text: 'Check this out',
    footer: 'Template footer',
    buttons: [
      { displayText: 'Visit Website', url: 'https://example.com', index: 0 },
      { displayText: 'Call Now', phoneNumber: '+1234567890', index: 1 },
      { displayText: 'Quick Reply', id: 'quick', index: 2 }
    ]
  }
})
```

### Button Reply Handling

When users tap buttons, you'll receive a `buttonsResponseMessage` or `templateButtonReplyMessage`:

```typescript
if (msg.message?.buttonsResponseMessage) {
  const selectedId = msg.message.buttonsResponseMessage.selectedButtonId
  console.log('Button selected:', selectedId)
}
```