---
title: Tworzenie reguł zaawansowanych dla arkuszy
description: Ta procedura prowadzi przez proces tworzenia zaawansowanych reguł dla arkuszy.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c06855c7a7648c5829b90bc548a7d2e400967698
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988609"
---
# <a name="create-advanced-rules-for-journals"></a>Tworzenie reguł zaawansowanych dla arkuszy

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi przez proces tworzenia zaawansowanych reguł dla arkuszy. Obejmuje skonfigurowanie kontroli arkusza i ograniczeń księgowania dla użytkowników. Procedura wykorzystuje dane firmy demonstracyjnej USMF.


## <a name="set-up-journal-control"></a>Konfigurowanie kontroli arkusza
1. W **Okienku nawigacji** otwórz **Moduły > Księga główna > Konfiguracja arkusza > Nazwy arkuszy**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. W **Okienku akcji** kliknij **Kontrola arkusza**.
4. W formularzu można zaksięgować skróconej karcie **Na jakiego typu kontach można księgować** kliknij przycisk **Dodaj**.
5. W polu **Firmy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. Na skróconej karcie **Które wartości segmentów są dozwolone dla tego arkusza** kliknij przycisk **Dodaj**.
9. W polu **Struktura konta** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Na liście znajdź i zaznacz odpowiedni rekord.
11. Na liście kliknij łącze w wybranym wierszu.
12. W polu **Segment** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
13. Na liście kliknij łącze w wybranym wierszu.
14. W polu **Od wartości** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście znajdź i zaznacz odpowiedni rekord.
16. Na liście kliknij łącze w wybranym wierszu.
17. W polu **Do wartości** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
18. Na liście znajdź i zaznacz odpowiedni rekord.
19. Na liście kliknij łącze w wybranym wierszu.

## <a name="set-up-posting-restrictions"></a>Konfigurowanie ograniczeń księgowania
1. Zamknij stronę.
2. Kliknij opcję **Ograniczenia księgowania**.
3. W polu **Jak chcesz skonfigurować ograniczenia księgowania** wybierz opcję „Według grupy użytkowników”.
4. W drzewie zaznacz grupę, której chcesz pozwolić na księgowanie w tym arkuszu.
5. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]