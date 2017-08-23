--- 
title: "Konfigurowanie ksiąg amortyzacji"
description: "W tym przewodniku po zadaniach zostanie utworzona nowa księga amortyzacji i skojarzona z grupą środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f8ca9cc59df4eab5a476524e92200687e5979bc9
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-depreciation-books"></a>Konfigurowanie ksiąg amortyzacji 

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach zostanie utworzona nowa księga amortyzacji i skojarzona z grupą środków trwałych.  Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.


## <a name="create-a-depreciation-book"></a>Tworzenie księgi amortyzacji
1. Wybierz kolejno opcje Środki trwałe > Ustawienia > Księgi amortyzacji.
2. Kliknij przycisk Nowy.
3. W polu Księga amortyzacji wpisz wartość.
4. Wypełnij pole Opis.
5. Zaznacz pole wyboru Oblicz amortyzację lub usuń jego zaznaczenie.
6. W polu Profil amortyzacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni profil amortyzacji.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Amortyzacja alternatywna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Na liście zaznacz odpowiedni profil amortyzacji.
11. Na liście kliknij łącze w wybranym wierszu.
    * Profil Amortyzacja dodatkowa będzie używany na potrzeby dodatkowej amortyzacji składnika aktywów w nadzwyczajnych okolicznościach. Na przykład może to służy do zarejestrowania amortyzacji powstałej w wyniku klęski żywiołowej.  
12. Zaznacz lub wyczyść pole wyboru Tworzenie korekt amortyzacji przy korektach podstawy.
13. W polu Kalendarz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
14. Na liście kliknij łącze w wybranym wierszu.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Kojarzenie księgi amortyzacji z grupą środków trwałych
1. Kliknij opcję Grupy środków trwałych.
2. W polu Grupa środków trwałych kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Konwencja amortyzacji wybierz opcję.
6. W polu Okres użytkowania wpisz liczbę.
    * Należy zauważyć, że wartość pola Okresy amortyzacji jest obliczana po ustawieniu okresu użytkowania.  


