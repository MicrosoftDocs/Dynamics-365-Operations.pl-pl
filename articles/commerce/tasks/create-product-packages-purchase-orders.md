---
title: Tworzenie pakietów produktów dla zamówień zakupu
description: Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu.
author: josaw1
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb10164be8d7a0828169cf3865f884afaa2e8408472edebe4cb0c7d4db059d8c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723244"
---
# <a name="create-product-packages-for-purchase-orders"></a>Tworzenie pakietów produktów dla zamówień zakupu

[!include [banner](../includes/banner.md)]

Ta procedura zawiera instruktaż tworzenia pakietu produktów i użycia go w zamówieniu zakupu. Zamówienie zakupu zostanie użyte do utworzenia zamówienia na wstępnie zdefiniowany zestaw produktów. Procedura wykorzystuje dane firmy demonstracyjnej USRT.


## <a name="create-a-product-package"></a>Tworzenie pakietu produktów
1. Wybierz kolejno opcje Retail i Commerce > Zarządzanie zapasami > Uzupełnienie > Pakiety produktów.
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

## <a name="add-package-to-purchase-order"></a>Dodawanie pakietu do zamówienia zakupu
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]