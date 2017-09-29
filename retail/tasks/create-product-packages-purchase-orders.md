--- 
title: "Tworzenie pakietów produktów dla zamówień zakupu"
description: "Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 695460415f81d65ec35eeee60209358b722c9244
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="create-product-packages-for-purchase-orders"></a>Tworzenie pakietów produktów dla zamówień zakupu

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu. Zamówienie zakupu zostanie użyte do utworzenia zamówienia na wstępnie zdefiniowany zestaw produktów. Procedura wykorzystuje dane firmy demonstracyjnej USRT.


## <a name="create-a-product-package"></a>Tworzenie pakietu produktów
1. Wybierz kolejno opcje Handel detaliczny i inny > Zarządzanie zapasami > Uzupełnienie > Pakiety produktów.
2. Kliknij przycisk Nowy.
3. W polu Numer paczki wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij łącze w wybranym wierszu.
7. Kliknij przycisk Dodaj.
8. W polu Numer towaru wpisz wartość „0160”.
9. W polu Rozmiar kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Na liście kliknij łącze w wybranym wierszu.
11. Wprowadź liczbę w polu Ilość.
12. Kliknij przycisk Dodaj.
13. W polu Numer towaru wpisz wartość „0160”.
14. W polu Numer wariantu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście kliknij łącze w wybranym wierszu.
16. Wprowadź liczbę w polu Ilość.
17. Kliknij przycisk Dodaj.
18. W polu Numer towaru wpisz wartość „0175”.
19. Wprowadź liczbę w polu Ilość.
20. Kliknij przycisk Zapisz.
21. Zamknij stronę.

## <a name="add-package-to-puchase-order"></a>Dodawanie pakietu do zamówienia zakupu
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście zaznacz tego samego dostawcę, dla którego wcześniej utworzono pakiet produktów, jeśli dostawca był wybrany.
5. Przełącz rozwinięcie sekcji Ogólne.
6. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście kliknij łącze w wybranym wierszu.
10. Kliknij przycisk OK.
11. Przełącz rozwinięcie sekcji Szczegóły wiersza.
12. Kliknij kartę Pakiety produktów.
13. Kliknij opcję Wiersz zamówienia zakupu.
14. Kliknij opcję Utwórz wiersze na podstawie paczki.
15. Na liście znajdź i zaznacz pakiet produktów utworzony w poprzednim kroku.
16. W polu Ilość wprowadź liczbę.
17. Kliknij przycisk Utwórz.
18. Kliknij przycisk Zapisz.

