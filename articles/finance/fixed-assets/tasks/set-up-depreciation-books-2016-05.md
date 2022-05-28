---
title: Konfigurowanie ksiąg amortyzacji
description: Ta procedura prowadzi proces tworzenia nowej księgi amortyzacji i kojarzy ją z grupą środków trwałych.
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a4713d949fe119cde1b1187a7c485d291281a8f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725660"
---
# <a name="set-up-depreciation-books"></a>Konfigurowanie ksiąg amortyzacji 

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi proces tworzenia nowej księgi amortyzacji i kojarzy ją z grupą środków trwałych. 

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
