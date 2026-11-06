# Rent Pal - WhatsApp Bot Progress Notes

**Project:** Rent Pal - peer-to-peer rental platform as a WhatsApp bot. Concept: koi apni zaroorat post karta hai (jaise football shoes), jiske paas item hai wo rent pe deta hai (per hour/day), platform commission kamata hai.

**Approach:** Meta WhatsApp Cloud API (official Meta/Facebook route)
**Last updated:** 6 Nov 2026

---

## Ho gaya (completed)

1. **Meta developer account ready** - developers.facebook.com pe login.
2. **Nayi app banayi: "Rent Pal"** - Create App se, use case: *Connect with customers through WhatsApp*.
3. **Business portfolio banaya: "RentPal"** - app creation ke dauran.
4. **API Setup page tak pahunche** - App Dashboard > WhatsApp use case > API Setup.
5. **Test number mila** - Meta ka test number From field mein aa gaya. Phone number ID aur Messaging account ID bhi page pe dikh rahe hain.
6. **Apna WhatsApp number recipient list mein add kiya** - test messages receive karne ke liye (1 of 5 recipients added).

## Abhi yahan atke hain (current blocker)

7. **Test message abhi tak successfully nahi gaya.** "Send message" dabane pe error aaya: *"Sending of message failed - unknown error (empty response)"*. Ye ek generic error hai - iski exact wajah confirm nahi hui.
8. **Ek restriction zaroor mili hai:** WhatsApp Manager mein Test Messaging Account pe likha hai **"Account restricted - Before you can begin messaging, you will need to verify your business."** Ye restriction account pe explicitly lagi hui hai; generic error ka definite reason yehi hai ya kuch aur, ye confirm nahi hai.
9. **Security Centre check kiya** - Business verification section mein RentPal **"Eligible for verification"** hai aur "Start verification" button mila. Button click karne ko bola gaya hai; **uske baad ka form abhi humne dekha nahi, toh koi submission confirm nahi hai.**

## Business verification ke baare mein (official Meta help se)

- Chahiye hoga: **legal business name, address, phone number, aur HTTPS website** - sab details legal business entity se exactly match karni chahiye.
- Agar Meta ko record na mile, toh **official documents** maang sakta hai (business license / registration waghera).
- Review mein **14 business days** tak lag sakte hain.
- **Important:** fake ya misleading details dene pe Meta verification reject kar sakta hai aur account pe action bhi le sakta hai. Toh real details hi lagani hain.
- Source: https://www.facebook.com/business/help/2058515294227817

## Abhi baaki hai (pending)

- [ ] Business verification ka decision - kya real registered business details available hain
- [ ] Pehla test message successfully bhejna
- [ ] Test message ka reply karna (isse 24-hour messaging window khulti hai)
- [ ] Webhook setup - taaki bot incoming messages receive kare (iske liye ek publicly reachable server chahiye hoga; hosting ke kai options hain, baad mein decide karenge)
- [ ] Suitable access token banana (sahi permissions aur lifetime ke saath)
- [ ] Bot ka actual logic - Rent Pal ka rent/lend flow

## Security notes

- **Access token chat/screenshots mein visible ho chuka hai.** Token kab expire hota hai ya purana token revoke kaise hota hai, ye humne officially verify nahi kiya - isliye ye matter abhi open hai, resolved nahi. Aage ke screenshots mein code/token wala box zaroor hide karo, aur token kabhi chat mein mat bhejo.
- Jab final access token banega, wo secure tareeke se handle karenge, chat mein nahi.

## Useful links

- Meta app dashboard: https://developers.facebook.com/apps
- Official setup guide: https://developers.facebook.com/documentation/business-messaging/whatsapp/get-started
- Business verification help: https://www.facebook.com/business/help/2058515294227817
