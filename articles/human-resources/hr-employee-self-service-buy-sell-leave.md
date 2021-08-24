---
title: Kupuj i sprzedawaj urlop
description: W ramach Dynamics 365 Human Resources można przesyłać żądania kupna i sprzedaży urlopu na podstawie zasad dotyczących kupna i sprzedaży, które zostały skonfigurowane przez firmę użytkownika.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1225bcfd0c7c9dfecde2aec54983fca8a298f1cf92d2929d8b1fbe2bdf05e5f9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779741"
---
# <a name="buy-and-sell-leave"></a>Kupuj i sprzedawaj urlop

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W ramach Dynamics 365 Human Resources można przesyłać żądania kupna i sprzedaży urlopu na podstawie zasad dotyczących kupna i sprzedaży, które zostały skonfigurowane przez firmę użytkownika.  

## <a name="request-to-buy-leave"></a>Wniosek o kupno urlopu

1. W obszarze roboczym **Samoobsługa pracownika etatowego** na kafelku **Wniosek o kupno urlopu** wybierz opcję **Zażądaj czasu wolnego**. 

2. Dodaj **Typ urlopu** i podaj **Ilość** dla czasu trwania urlopu, który chcesz kupić. 

3. Gdy masz wszystko gotowe do wysłania wniosku, naciśnij przycisk **Prześlij**. 

Salda będą aktualizowane automatycznie lub przejdą przez proces zatwierdzenia przed aktualizacją. Zależy to od konfiguracji zasady kupowania.

## <a name="request-to-sell-leave"></a>Wniosek o sprzedaż urlopu

1. W obszarze roboczym **Samoobsługa pracownika etatowego** na kafelku **Wniosek o sprzedaż urlopu** wybierz opcję **Zażądaj czasu wolnego**. 

2. Dodaj **Typ urlopu** i podaj **Ilość** dla czasu trwania urlopu, który chcesz sprzedać. 

3. Gdy masz wszystko gotowe do wysłania wniosku, naciśnij przycisk **Prześlij**.

Salda będą aktualizowane automatycznie lub przejdą przez proces zatwierdzenia przed aktualizacją. Zależy to od konfiguracji zasady kupowania.


## <a name="troubleshooting"></a>Rozwiązywanie problemów 

Jeśli przepływ żądania opuszczenia sklepu nie powiedzie się, użytkownicy z uprawnieniem **EssLeaveBuySellRequestApprover** mogą przeglądać logi wszystkich żądań opuszczenia sklepów. Aby to zrobić, wejdź na **Urlop i nieobecność > Link > Kupno i sprzedaż wniosków o urlop > Dziennik wiadomości** (w lewym górnym rogu). **Dziennik komunikatów** pokazuje użytkownikom sposób przetwarzania transakcji oraz skojarzonej historii przepływu pracy.


## <a name="see-also"></a>Informacje dodatkowe

[Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)</br>
[Zarządzaj zasadami zakupu i sprzedaży urlopu](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
