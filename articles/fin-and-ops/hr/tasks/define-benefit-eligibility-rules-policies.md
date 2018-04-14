--- 
title: "Definiowanie zasad i reguł uprawnień do świadczenia"
description: "W tym nagraniu pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c570574d15bbc55b4d0d79b8e62d74adcc15b387
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definiowanie zasad i reguł uprawnień do świadczenia

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tym nagraniu pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.  

Dane wykorzystane do stworzenia tego nagrania pochodzą z firmy demonstracyjnej USMF.


## <a name="create-benefit-eligibility-policy-rule-type"></a>Tworzenie typu reguły uprawnienia do świadczenia
1. Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Typy reguł uprawnień do świadczenia.
2. Kliknij przycisk Nowy.
3. W polu Nazwa reguły wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Nazwa kwerendy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij łącze w wybranym wierszu.
7. Kliknij przycisk Zapisz.
8. Zamknij stronę.

## <a name="benefit-eligibility-policy"></a>Zasady uprawnienia do świadczenia
1. Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Zasady uprawnienia do świadczenia.
2. Wybierz istniejącą zasadę świadczenia.
3. Na liście kliknij łącze w wybranym wierszu.
4. Przełącz rozwinięcie sekcji Organizacje zasad.  W tym miejscu można dodać lub usunąć wszelkie organizacje, które mają zostać uwzględnione w zasadach.
5. Rozwiń lub zwiń sekcję Reguły zasad.
6. Na liście odszukaj utworzoną wcześniej regułę.
7. Kliknij przycisk Utwórz regułę.
8. W polu Data obowiązywania wprowadź dzień, od którego zasada ma obowiązywać.
    * Ustawienie dat obowiązywania i zakończenia umożliwi wprowadzanie w przyszłości zmian w regułach i wyeliminowanie potrzeby wracania do zasad, jeśli zechcesz, aby te zmiany zaczęły obowiązywać.  
9. 
    * Na przykład jeżeli chcesz, aby reguła była stosowana tylko do menedżerów sprzedaży, można utworzyć klauzulę Where o treści: Where opis stanowiska równa się Menedżer sprzedaży.  W regule można dodać wiele instrukcji Where z operatorami And lub Or.  
10. Kliknij przycisk OK.
11. Zamknij stronę.
12. Zamknij stronę.

## <a name="assign-rule-to-benefit"></a>Przypisywanie reguły do świadczenia
1. Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Świadczenia.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Rozwiń lub zwiń sekcję Reguły uprawnienia.
5. Kliknij przycisk Edytuj.
6. W polu Uprawnienie na liście zaznacz opcję Oparte na regułach.
7. W polu Typ reguły kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.
9. Na liście kliknij łącze w wybranym wierszu.
10. Kliknij przycisk Zapisz.
11. Zamknij formularz.


