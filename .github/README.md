# 💬 Chrome Hearts - Bot WhatsApp Avanzato

> **Il bot WhatsApp più fluido e reattivo che tu abbia mai visto**

Benvenuto in Cheome Hearts! Un bot WhatsApp super potente costruito con **Baileys**, che sfrutta le ultime tecnologie per offrirti un'esperienza senza pari.

---

## 🌟 Cosa Rende Speciale Chrome Hearts?

✨ **Supporto LID/PN Intelligente**
- Auto-routing verso dispositivi e numeri di telefono
- Messaggi sempre indirizzati correttamente
- Zero ritardi, massima fluidità

⚡ **Pulsanti Interattivi**
- CTA URL per link e azioni web
- Call buttons per contatti telefonici
- Quick reply per risposte veloci

🎯 **Context Aware**
- Ricorda il contesto delle conversazioni
- Mantiene le informazioni dei dispositivi collegati
- Messaggi sempre coerenti e naturali

---

## 🚀 Inizia Subito

### Messaggi con Pulsanti Quick Reply

```typescript
await sock.sendMessage(jid, {
  buttonsMessage: {
    text: '🎉 Scegli un\'opzione:',
    footer: 'Cheome Hearts',
    buttons: [
      { displayText: '✅ Opzione 1', id: 'opt1' },
      { displayText: '🎯 Opzione 2', id: 'opt2' }
    ]
  }
})
```

### Messaggi Template con URL e Chiamate

```typescript
await sock.sendMessage(jid, {
  templateMessage: {
    text: '👋 Scopri di più!',
    footer: 'Powered by Cheome Hearts',
    buttons: [
      { displayText: '🌐 Visita il Sito', url: 'https://example.com', index: 0 },
      { displayText: '📞 Chiamami', phoneNumber: '+1234567890', index: 1 },
      { displayText: '💬 Richiedi Info', id: 'info', index: 2 }
    ]
  }
})
```

### Gestire le Risposte ai Pulsanti

```typescript
if (msg.message?.buttonsResponseMessage) {
  const selectedId = msg.message.buttonsResponseMessage.selectedButtonId
  console.log('❤️ Pulsante premuto:', selectedId)
  // Reagisci al pulsante selezionato!
}
```

---

## 💡 Funzionalità Avanzate

### 🔗 Supporto LID (Linked Device ID)

Il bot gestisce automaticamente:
- **LID/PN Addressing**: Routing intelligente verso telefoni e dispositivi
- **Participant Mapping**: MapPing perfetto dei partecipanti
- **Context Preservation**: Le informazioni non vanno mai perse

### 📨 Messaggi Fluidi

Con Cheome Hearts, i tuoi messaggi:
- Arrivano sempre al destinatario giusto
- Mantengono il contesto della conversazione
- Rispondono istantaneamente

---

## 📦 Cosa Include?

- ✅ TypeScript completo per sicurezza massima
- ✅ WebSockets per latenza ultrabassa
- ✅ Supporto LID/PN per routing intelligente
- ✅ Pulsanti interattivi (URL, chiamate, quick reply)
- ✅ Gestione automatica del contesto
- ✅ Error handling robusto

---

## 🎮 Esempi di Utilizzo

### Bot Assistente
```typescript
sock.ev.on('messages.upsert', async (m) => {
  const msg = m.messages[0]
  
  if (msg.message?.buttonsResponseMessage) {
    switch (msg.message.buttonsResponseMessage.selectedButtonId) {
      case 'opt1':
        await sock.sendMessage(msg.key.remoteJid!, 
          { text: '❤️ Hai scelto l\'opzione 1!' })
        break
      case 'opt2':
        await sock.sendMessage(msg.key.remoteJid!, 
          { text: '🎯 Hai scelto l\'opzione 2!' })
        break
    }
  }
})
```

---

## 🔥 Perché Chrome Hearts?

| Feature | Chrome Hearts | Altro |
|---------|--------------|-------|
| Supporto LID | ✅ Nativo | ❌ Parziale |
| Pulsanti Interattivi | ✅ 3 Tipi | ⚠️ 1-2 Tipi |
| Fluidità | ✅ Ultra-rapido | ❌ Lento |
| Context Aware | ✅ Totale | ⚠️ Parziale |
| Aggiornamenti | ✅ Frequenti | ❌ Rari |

---

## 📞 Supporto & Comunità

- 💬 Discord:@effettuo)
- 📚 Docs: Soon...

---


---

**Made with ❤️ by Chrome Hearts**

*Costruito sulla fondamenta robuste di Baileys*
