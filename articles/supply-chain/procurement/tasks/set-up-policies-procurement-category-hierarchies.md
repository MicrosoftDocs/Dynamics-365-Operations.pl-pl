---
title: Konfigurowanie zasad dla hierarchii kategorii zaopatrzenia
description: Niniejszej procedury należy użyć w celu skonfigurowania reguły dla zamówionych produktów z kategorii.
author: GalynaFedorova
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2a8248374f34e0937aa569259c5925506857ddd
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675915"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Konfigurowanie zasad dla hierarchii kategorii zaopatrzenia

[!include [banner](../../includes/banner.md)]

Niniejszej procedury należy użyć w celu skonfigurowania reguły dla zamówionych produktów z kategorii. Reguły są definiowane dla określonej zasady zakupów. Reguła dostępu do kategorii określa kategorie zaopatrzenia, do których mają dostęp pracownicy podczas tworzenia zapotrzebowania. Gdy pracownik tworzy zapotrzebowanie, stosowana zasada zakupów i reguła dostępu do kategorii zależą od firmy i jednostki operacyjnej, do której należy pracownik. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. To zadanie zazwyczaj wykonuje kierownik ds. zakupów.


## <a name="find-the-procurement-policy"></a>Znajdowanie zasad zaopatrzenia
1. W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Ustawienia > Zasady > Zasady zakupów**.
2. Kliknij łącze na zasadzie Procurement Policy USMF. To jest zasada, do której dodasz regułę. Musi to być aktywna zasada.  

## <a name="create-a-category-access-rule"></a>Tworzenie reguły dostępu do kategorii
1. Rozwiń kartę skróconą **Reguły zasad**.
2. Na liście **Typ reguły** zaznacz element **Reguła dostępu do kategorii**. Jeśli przycisk **Utwórz regułę** jest wygaszony, oznacza to, że już istnieje aktywna reguła dostępu do Kategorii. Sprawdź wartości w polach **Data obowiązywania** i **Data ważności**, aby określić, która data powoduje problem, zaznacz ją, a następnie kliknij przycisk **Wycofanie reguły**. Jeśli przycisk **Utwórz regułę** jest dostępny, nie trzeba podejmować żadnych działań.  
3. Kliknij przycisk **Utwórz regułę**.
4. W polu **Data obowiązywania** wprowadź datę i godzinę. Czas nie może się pokrywać z inną regułą, która jest już aktywna.  
5. Wybierz kategorię, której będzie dotyczyć reguła. Zapamiętaj lub zapisz, która to kategoria — będzie to później potrzebne. Po wybraniu kategorii jej wszystkie kategorie nadrzędne są również dodawane do listy Wybrane kategorie. Aby zastosować regułę do wszystkich podkategorii wybranej kategorii, zaznacz pole wyboru **Uwzględnij podkategorie**.
6. Kliknij strzałkę w prawo, aby dodać do listy **Wybrane kategorie**.  
4. Kliknij przycisk **OK**. Jeśli w opcji **Uwzględnij regułę** nadrzędną zaznaczysz wartość Tak, reguła zdefiniowana przez Ciebie dla kategorii nadrzędnej zostanie przypisana również do jej kategorii podrzędnych, jeśli kategorie podrzędne nie mają zdefiniowanej żadnej reguły.

## <a name="create-a-category-policy-rule"></a>Tworzenie reguły dla kategorii
1. Na liście **Typ reguły** zaznacz element **Reguła kategorii**. Jeśli przycisk **Utwórz regułę jest** wyszarzony, zaznacz aktywną regułę, a następnie kliknij opcję **Wycofanie reguły**.  
2. Kliknij przycisk **Utwórz regułę**.
3. W polu **Data obowiązywania** wprowadź datę i godzinę.
4. Kliknij przycisk **Dodaj**.
5. W polu **Kategoria** zaznacz tę samą kategorię, jak użyta w **regule dostępu kategorii**.
6. W polu **Wybór dostawcy** wybierz opcję. Zaznacz regułę mającą kontrolować, jakiego rodzaju dostawców można wybierać dla kategorii podczas tworzenia zapotrzebowań.  
7. Kliknij przycisk **Zamknij**. Zdefiniowane przez Ciebie reguły dotyczą zapotrzebowań typu Zużycie. Jeśli trzeba zdefiniować zasady dla zapotrzebowań typu Uzupełnienie zapasów, należy utworzyć regułę dla typu reguły o nazwie „Reguła dostępu do kategorii uzupełniania”.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]