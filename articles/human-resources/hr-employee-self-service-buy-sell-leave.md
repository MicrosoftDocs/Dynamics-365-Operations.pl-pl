---
title: Kupuj i sprzedawaj urlop
description: W tym artykule opisano sposób przesyłania wniosków o zakup i sprzedaż urlopów w Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a6d38a69a73ce14f099beb6b6b560bf6c5686b0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875721"
---
# <a name="buy-and-sell-leave"></a>Kupuj i sprzedawaj urlop


>[!Important]
>Funkcjonalność opisana w tym artykule jest obecnie dostępna dla klientów samodzielnej wersji Dynamics 365 Human Resources. Część lub całość tej funkcjonalności będzie dostępna w ramach przyszłego wydania infrastruktury Finance po wydaniu wersji Finance 10.0.26.

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
