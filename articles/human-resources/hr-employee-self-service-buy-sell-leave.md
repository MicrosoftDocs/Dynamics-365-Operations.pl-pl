---
title: Kupuj i sprzedawaj urlop
description: W tym temacie opisano sposób przesyłania wniosków o zakup i sprzedaż urlopów w Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2ddc50540ba0686f18b6e8875e40f11c378c448f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067486"
---
# <a name="buy-and-sell-leave"></a>Kupuj i sprzedawaj urlop


[!INCLUDE [PEAP](../includes/peap-2.md)]

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

Jeśli przepływ żądania opuszczenia sklepu nie powiedzie się, użytkownicy z uprawnieniem **EssLeaveBuySellRequestApprover** mogą przeglądać logi wszystkich żądań opuszczenia sklepów. Aby to zrobić, wejdź na **Urlop i nieobecność > Linki > Kupno i sprzedaż wniosków o urlop > Dziennik wiadomości** (w lewym górnym rogu). **Dziennik komunikatów** pokazuje użytkownikom sposób przetwarzania transakcji oraz skojarzonej historii przepływu pracy.


## <a name="see-also"></a>Informacje dodatkowe

[Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)</br>
[Zarządzaj zasadami zakupu i sprzedaży urlopu](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
