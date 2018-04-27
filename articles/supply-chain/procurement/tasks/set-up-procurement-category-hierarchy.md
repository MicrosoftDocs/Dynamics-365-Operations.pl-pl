--- 
title: Ustawianie hierarchii kategorii zaopatrzenia
description: "W tej procedurze pokazano, jak utworzyć nowe węzły w hierarchii kategorii zaopatrzenia oraz jak skonfigurować kategorię zaopatrzenia, która ma być używana w procesie zaopatrzenia."
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6ad5c8552a6989e9093d0b1325754bc0f6d19372
ms.openlocfilehash: 4541d029c9c3be3ee42332e5d8ff183dd503f13e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a>Ustawianie hierarchii kategorii zaopatrzenia

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak utworzyć nowe węzły w hierarchii kategorii zaopatrzenia oraz jak skonfigurować kategorię zaopatrzenia, która ma być używana w procesie zaopatrzenia. Te zadania zazwyczaj wykonuje menedżer ds. zakupów. Przed rozpoczęciem tej procedury musi istnieć hierarchia kategorii typu Zaopatrzenie. Jeśli używasz danych firmy demonstracyjnej, procedurę można wykonać w firmie USMF.


## <a name="add-a-new-procurement-category"></a>Dodawanie nowej kategorii zaopatrzenia
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Kategorie zaopatrzenia.
2. Kliknij opcję Edytuj hierarchię kategorii.
    * Bieżąca hierarchia kategorii zaopatrzenia zostanie wyświetlona przy lewej krawędzi strony. Zmodyfikujesz tę hierarchię.  
3. Kliknij opcję Nowy węzeł kategorii.
    * Domyślnie system wybiera węzeł najwyższego poziomu. Jeśli wykonujesz tę procedurę w przewodniku po zadaniach, możesz kliknąć przycisk Odblokuj i wybrać inny węzeł nadrzędny, aby wstawić tam swój nowy węzeł. Po wykonaniu tej operacji ponownie zablokuj przewodnik po zadaniach, a następnie kliknij przycisk Nowy węzeł kategorii.  
4. W polu Nazwa wpisz wartość.
5. Wypełnij pole Opis.
6. W polu Przyjazna nazwa wpisz wartość.
    * Przyjazna nazwa jest opcjonalna. Będzie wyświetlany w wyszukiwaniach kategorii wraz z nazwą kategorii.  
7. Kliknij przycisk Zapisz.

## <a name="add-products-to-your-new-procurement-category"></a>Dodawanie produktów do nowej kategorii zaopatrzenia
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Kategorie zaopatrzenia.
    * Zaznacz dodany właśnie węzeł. Jeśli wykonujesz tę procedurę w przewodniku po zadaniach, może być konieczne odblokowanie przewodnika po zadaniach w celu wybrania węzła.  
2. Przełącz rozwinięcie sekcji Produkty.
3. Kliknij przycisk Dodaj, aby skojarzyć produkty z kategorią zaopatrzenia.
4. Zaznacz produkt, który ma zostać dodany do kategorii zaopatrzenia.
5. Kliknij strzałkę, aby wybrać produkt.
6. Zaznacz kolejny produkt, który ma zostać dodany do kategorii zaopatrzenia.
7. Kliknij strzałkę, aby wybrać produkt.
8. Kliknij przycisk OK.

## <a name="add-approved-and-preferred-vendors"></a>Dodawanie zatwierdzonych i preferowanych dostawców
1. Przełącz rozwinięcie sekcji Dostawcy.
2. Kliknij przycisk Dodaj.
    * Można dodać dostawcę do kategorii zaopatrzenia i określić, czy jest on preferowany czy tylko zatwierdzony dla kategorii. Usunięcie dostawcy z kategorii nie powoduje usunięcia historycznych transakcji z dostawcą w danej kategorii.   
3. Znajdź dostawcę, który ma zostać dodany do kategorii zaopatrzenia.
4. Kliknij strzałkę, aby wybrać dostawcę.
5. Kliknij przycisk OK.
6. Wybierz wiersz dostawcy, którego chcesz zmodyfikować.
7. W polu Stan dostawcy wybierz opcję.
    * Ustawienie wyboru dostawcy w reguły kategorii decyduje, czy w zapotrzebowaniach na zakup są dostępni dostawcy preferowani, zatwierdzeni czy wszyscy.   

## <a name="add-additional-information-to-the-category"></a>Dodawanie uzupełniających informacji do kategorii
1. Przełącz rozwinięcie sekcji Grupy kryteriów oceny dostawców.
    * Ta karta umożliwia określenie kryteriów, według których należy oceniać dostawców w kategorii zaopatrzenia. W tym celu kliknij przycisk Dodaj, a następnie wybierz grupę oceny dostawców zawierającą żądane kryteria.  
2. Przełącz rozwinięcie sekcji Kwestionariusze.
    * Ta karta umożliwia dodawanie kwestionariuszy, które będą wyświetlane w zapotrzebowaniu, o ile w polu Typu działania zaznaczysz wartość „Zapotrzebowanie”. Wtedy zleceniodawca musi wypełnić kwestionariusz, zanim wyśle zapotrzebowanie na określony produkt lub produkty z kategorii zaopatrzenia.  
3. Przełącz rozwinięcie sekcji Grupy podatków dla towaru.
4. W polu Grupa podatków dla towaru: kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Umożliwia wybranie grupy podatków.
6. Przełącz rozwinięcie sekcji Strona kategorii.
    * Strony kategorii tworzy się na stronie Hierarchia kategorii. Zawierają one informacje o kategorii zaopatrzenia, takie jak typy produktów w kategorii, zdjęcia produktów w kategorii lub ogłoszenia np. o rabatach dostępnych w danej kategorii. Informacje na stronie kategorii są wyświetlane w zapotrzebowaniach na zakup.  
7. Zamknij stronę.


