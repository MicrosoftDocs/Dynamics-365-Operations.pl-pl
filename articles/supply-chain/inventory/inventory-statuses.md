---
title: "Stany zapasów"
description: "W tym artykule opisano, jak za pomocą stanów zapasów klasyfikować i śledzić zapasy."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 70b084ac2eb8ffbd8832df2e562e8862e4ac8e57
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="inventory-statuses"></a>Stany zapasów

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak za pomocą stanów zapasów klasyfikować i śledzić zapasy.

Stany zapasów służą do kategoryzowania zapasów. Można następnie zainicjować odpowiednie działania, takie jak uzupełnienie zapasów czy praca odłożenia.

Oto kilka przykładów zastosowania stanów zapasów:

-   Tworzenie stanów zapasów dla dostępnych zapasów, transakcji przychodzących i wychodzących.
-   Określanie domyślnego stanu zapasów dla transakcji magazynowych.
-   Zmiana stanu zapasów dla towarów przed przyjęciem, podczas przyjęcia lub gdy są odłożone w ramach przesunięcia zapasów.
-   Stan zapasów służy do wyceny towarów, gdy zostaną one zwrócone, i do planowania zapotrzebowania na towar podczas planowania głównego.

Stan zapasów jest jednym z wymiarów w grupie wymiarów magazynowania. Stany zapasów można sklasyfikować jako dostępne i niedostępne i można używać parametru **Blokowanie zapasów**, aby blokować towary z niedostępnym stanem zapasów. Pozycje ze stanem zablokowanym są uznawane za zapasy fizyczne i nie można ich użyć w zleceniu produkcyjnym, zamówieniu sprzedaży ani transakcji wychodzącej.

Można korzystać z pozycji magazynowych ze stanem niedostępne lub dostępne w przypadku pracy przychodzącej. Można na przykład utworzyć stan dostępny o nazwie **Gotowe**, stan niedostępny o nazwie **Uszkodzone** i stan zablokowany o nazwie **Zablokowane**. Podczas tworzenia zamówienia zakupu dla odebranych lub zwróconych towarów, jeśli wszystkie towary są uszkodzone, można zmienić stan zapasów tych towarów na **Uszkodzone** w wierszu zamówienia zakupu. Po przyjęciu tych towarów ich stan jest automatycznie ustawiany na **Zablokowane**. W przypadku zeskanowania uszkodzonych towarów za pomocą urządzenia przenośnego program Microsoft Dynamics 365 for Finance and Operations może użyć dyrektywy lokalizacji i szablonów pracy, aby wyświetlić informacje o odpowiedniej lokalizacji lub zakresie lokalizacji, w których można odłożyć te towary. W przypadku zwróconych towarów na stronie **Transakcje magazynowe** tworzony jest typ **Rezerwacja**.

W przypadku pracy wychodzącej należy użyć towarów z dostępnym stanem zapasów. Jeśli masz towary ze stanem **Uszkodzone** i zostało dla nich uruchomione planowanie główne, pozycje te zostaną uznane za brakujące, a zapasy są uzupełniane automatycznie.

Po skonfigurowaniu stanów zapasów można ustawić domyślny stan zapasów dla oddziału, towaru i magazynu. Można również ustawić domyślny stan dla zamówień sprzedaży, przeniesienia i zakupu. Domyślny stan dla zamówień sprzedaży i wychodzących zamówień przeniesienia opcja **Blokowanie towarów** nie może mieć wartości **Tak**. Stan zapasów przejmowany z domyślnych ustawień lokalizacji, magazynu, towaru, zamówienia zakupu, zamówienia przeniesienia czy zamówienia sprzedaży może zostać zmieniony za pomocą urządzenia przenośnego lub w wierszu zamówienia zakupu, zamówienia sprzedaży lub zamówienia przeniesienia.

Aby zaplanować zapotrzebowanie na towary z dostępnym stanem zapasów, należy wybrać opcję **Plan zapotrzebowania wg wymiaru** dla wymiaru magazynowego na stronie **Grupy wymiarów magazynowania**. Po otwarciu **Kreatora zapotrzebowania na towar** towary z dostępnym stanem pojawiają się na stronie **Stan**. Do tworzenia ustawień zapotrzebowania dla tych pozycji wybierz identyfikator stanu zapasów dla dostępnych zapasów. Zgodnie z ustawieniami zapotrzebowania, można obliczać zapotrzebowania na pozycje i prognozować dostawy oraz popyt na dostępne towary podczas planowania głównego. Nie można utworzyć ustawienia zapotrzebowania na towary ze stanem zablokowanym. Alternatywnie można użyć strony **Zapotrzebowanie na towar**, aby utworzyć lub zmodyfikować parametry zapotrzebowania na towar.

