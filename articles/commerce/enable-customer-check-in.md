---
title: Włączanie powiadomień zameldowania odbiorcy w punkcie sprzedaży
description: W tym temacie opisano sposób włączania powiadomień zameldowania odbiorcy w punkcie sprzedaży systemu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e4defc15d9ef198a361934d51e31016747dbb5ab
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937609"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Włączanie powiadomień zameldowania odbiorcy w punkcie sprzedaży

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano sposób włączania powiadomień zameldowania odbiorcy w punkcie sprzedaży systemu Microsoft Dynamics 365 Commerce.

W wiadomościach e-mail „zamówienie gotowe do odbioru” organizacje mogą zamieścić łącze lub przycisk, aby klienci powiadomili sklep, że znajdują się w budynku i oczekują na przyniesienie paczki. Odbiorcy otrzymają następnie potwierdzenie zameldowania, a sklep otrzyma powiadomienie jako zadanie w aplikacji punktu sprzedaży. To zadanie służy jako monit o skojarzenie sprzedaży w celu dostarczenia zamówienia do pojazdu odbiorcy. Wtedy odbiorca nie musi wchodzić do sklepu.

Przepływ pracy zameldowania odbiorcy można również skonfigurować w taki sposób, aby gromadził od odbiorców dodatkowe informacje, takie jak numer miejsca parkingowego, marka, model i kolor jego pojazdu oraz instrukcje dostawy. Informacje te mogą ułatwić sprzedawcy realizację zamówienia.

## <a name="enable-customer-check-in"></a>Włączanie zameldowania odbiorcy

Po włączeniu funkcji zameldowania odbiorcy Commerce generuje identyfikator potwierdzenia zamówienia (nazywany także identyfikatorem odwołania do kanału). Ponadto generuje identyfikatory potwierdzenia zamówienia dla zamówień, które są tworzone za pośrednictwem punktu sprzedaży (POS) lub kanałów w centrum obsługi. 

Aby włączyć funkcję zameldowania odbiorcy w centrali Commerce, wykonaj następujące kroki.

1. Kliknij kolejno opcje **Obszary robocze \> Zarządzanie funkcjami**.
2. Wyszukaj funkcję **Generowanie jednolitego formatu identyfikatora odwołania do kanału w różnych kanałach**. 
3. Wybierz funkcję, a następnie w okienku właściwości naciśnij przycisk **Włącz teraz**. 

## <a name="create-a-check-in-confirmation-page"></a>Tworzenie strony potwierdzenia zameldowania

W witrynie handlu elektronicznego trzeba utworzyć nową stronę, która będzie stanowiła środowisko potwierdzenia zameldowania. Po dodatkowej konfiguracji strona może również zawierać formularz, który zbiera dodatkowe informacje od odbiorców, które ułatwią realizację zamówienia. Aby uzyskać informacje dotyczące sposobu skonfigurowania strony i modułu, zobacz [Moduł zameldowania odbiorcy](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Konfigurowanie szablonu transakcyjnej wiadomości e-mail

Musisz dodać łącze lub przycisk **Jestem tutaj** do szablonu transakcyjnej wiadomości e-mail, którą odbiorcy otrzymują, gdy ich zamówienie jest gotowe do odbioru. Odbiorcy będą używać tego łącza lub przycisku w celu powiadomienia sklepu, że przybyli, aby odebrać zamówienie. 

Dodaj łącze lub przycisk do szablonu, który jest mapowany na typ powiadomienia **Zakończenie pakowania** i tryb dostawy używany do realizacji zamówienia „przy krawężniku”. W szablonie utwórz łącze lub przycisk HTML, który wskazuje adres URL utworzonej strony potwierdzenia zameldowania. Oto przykład.

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
Aby uzyskać więcej informacji dotyczących konfigurowania szablonów wiadomości e-mail, zobacz temat [Dostosowywanie transakcyjnych wiadomości e-mail zależnie od trybu dostawy](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>W punkcie sprzedaży zostanie utworzone zadanie potwierdzenia zameldowania

Gdy odbiorca powiadomi sklep, że jest obecny do odbioru, otrzyma powiadomienie o potwierdzeniu zameldowania i na liście zadań w punkcie sprzedaży dla sklepu, w którym odbiorca odbiera zamówienie, zostanie utworzone zadanie. Zadanie zawiera wszystkie informacje o odbiorcy i zamówieniu wymagane do realizacji zamówienia. W zadaniu w polu instrukcji są podane wszystkie informacje zebrane od odbiorcy za pośrednictwem formularza informacji dodatkowych. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł zameldowania do odbioru](check-in-pickup-module.md)
