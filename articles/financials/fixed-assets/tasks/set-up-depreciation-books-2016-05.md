--- 
title: "Konfigurowanie ksiąg amortyzacji (maj 2016)"
description: "W tym przewodniku po zadaniach zostanie utworzona nowa księga amortyzacji i skojarzona z grupą środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-depreciation-books-may-2016"></a>Konfigurowanie ksiąg amortyzacji (maj 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


