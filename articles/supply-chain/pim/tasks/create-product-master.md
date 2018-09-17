--- 
title: "Tworzenie produktu głównego"
description: "Utwórz produkt główny dla wstępnie zdefiniowanych wariantów."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f944258e7efdd5c9eba7daf9a80c67058a6cc055
ms.openlocfilehash: 6e5cf92f7736523faf25ac97278a8a273e14ff88
ms.contentlocale: pl-pl
ms.lasthandoff: 10/25/2017

---
# <a name="create-a-product-master"></a>Tworzenie produktu głównego

[!include [task guide banner](../../includes/task-guide-banner.md)]

Utwórz produkt główny dla wstępnie zdefiniowanych wariantów. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla projektanta produktów.


## <a name="create-a-new-product-master"></a>Tworzenie nowego produktu głównego
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkty > Produkty główne.
2. Kliknij przycisk Nowy.
3. W polu Numer produktu wpisz wartość.
    * Numer musi być unikatowy. Dla pola Numer produktu można określić sekwencję numeracji. W takim przypadku użytkownik nie musi wprowadzać wartość.  
4. W polu Nazwa produktu wpisz wartość.
    * Wprowadź opisową nazwę produktu. Domyślna jest to nazwa wyszukiwania, ale użytkownik może to zmienić.  
5. W polu Grupa wymiarów produktu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa wymiarów produktu określa, który z 4 wymiarów produktu może być używane do tworzenia wariantów produktu. W tym przykładzie użyto grupy z kolorem i rozmiarem.  
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
    * Domyślną technologią konfiguracji jest Wstępnie zdefiniowany wariant. Będzie ona używana w tym przykładzie.  
8. Kliknij przycisk OK.

## <a name="select-product-dimension-groups"></a>Wybór grup wymiarów produktów
1. W polu Grupa kolorów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. W polu Grupa rozmiarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
6. Na liście kliknij łącze w wybranym wierszu.

## <a name="add-dimension-groups"></a>Dodawanie grup wymiarów
1. W okienku akcji kliknij pozycję Produkt.
2. Kliknij przycisk Grupy wymiarów, aby otworzyć rozwijane okno dialogowe.
3. W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wymiary magazynowania umożliwiają sterowanie sposobem przechowywania towarów w magazynie i sposobem ich pobierania. Na przykład wymiar magazynowania może obejmować oddział i magazyn.  
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa wymiarów śledzenia określa wymiary śledzenia, które można dodawać do produktu. Na przykład numer partii i numer seryjny mogą służyć do śledzenia pozycji magazynowych.  
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. Kliknij przycisk OK.
10. Kliknij przycisk Zapisz.
11. Zamknij stronę.


