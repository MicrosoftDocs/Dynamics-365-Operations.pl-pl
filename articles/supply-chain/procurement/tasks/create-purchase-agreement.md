---
title: Tworzenie umowy zakupu
description: Ta procedura przeprowadzi Cię przez proces tworzenia umowy zakupu.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b317f0a0fc8f198bad9501f325557ac2a4796989
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547636"
---
# <a name="create-a-purchase-agreement"></a>Tworzenie umowy zakupu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przeprowadzi Cię przez proces tworzenia umowy zakupu. Zazwyczaj robi to kierownik ds. zakupów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem trzeba mieć skonfigurowaną klasyfikacji umów zakupu. Po utworzeniu umowy można jej używać podczas tworzenia zamówienia zakupu. Spowoduje to skopiowanie warunków umowy do nagłówka oraz do wszystkich wierszy w zamówieniu, których dotyczy umowa.


## <a name="create-a-new-purchase-agreement"></a>Tworzenie nowej umowy zakupu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Umowy zakupu > Umowy zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Klasyfikacja umowy zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. Rozwiń sekcję Ogólne.
10. W polu Data wygaśnięcia wprowadź datę.
    * Ta data ważności będzie domyślna dla wszystkich wierszy zobowiązań i określi, jak długo każde konkretne zobowiązanie jest ważne.  
11. W polu Tytuł dokumentu nadaj nazwę umowie zakupu.
    * Pozostaw w polu Domyślne zobowiązanie wartość Zobowiązanie co do ilości produktu (lub ją zmień na tą, jeśli jest ustawiona inna).  
    * Domyślna wartość zobowiązania określa opcje dostępne w wierszach umowy. Jeśli przy tworzeniu wierszy umowy potrzebujesz nowego typu zobowiązania, należy zmienić domyślne zobowiązanie w nagłówku.  Istnieją 4 rodzaje zobowiązań: Zobowiązanie co do ilości produktu — na określoną ilość produktu; Zobowiązanie co do wartości produktu — na określoną wartość produktu w walucie; Zobowiązanie co do wartości w ramach kategorii produktu — na wartość produktu w określonej walucie w kategorii zaopatrzenia, gdzie kwota może dotyczyć towaru z katalogu lub spoza katalogu; Zobowiązanie co do wartości — na określoną kwocie w walucie, która może być pokryta przez jakikolwiek produkt z dowolnej kategorii zaopatrzenia.  
12. Kliknij przycisk OK.

## <a name="add-a-commitment"></a>Dodawanie zobowiązania
1. Kliknij przycisk Dodaj wiersz.
2. Na liście oznacz wybrany wiersz.
3. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Wybierz produkt, dla którego chcesz dodać zobowiązanie.
5. Na liście kliknij łącze w wybranym wierszu.
6. Wprowadź liczbę w polu Ilość.
    * Jest to ilość całkowita, jaką zgodzono się kupić od dostawcy.  
7. Wprowadź liczbę w polu Cena jednostkowa.
8. Rozwiń sekcję Szczegóły wiersza.
9. W opcji Wymuszono maks. zaznacz wartość Tak.
    * Opcja Wymuszono maks. ogranicza użycie zobowiązania. Można kupować tylko do ilości określonej w polu Ilość dla wiersza.  
10. Zwiń sekcję Szczegóły wiersza.

## <a name="add-header-conditions"></a>Dodawanie warunków nagłówka
1. W okienku akcji kliknij pozycję Opcje.
2. Kliknij przycisk Zmień widok.
3. Kliknij opcję Widok nagłówka.
4. Rozwiń sekcję Warunki.
5. W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * W tym miejscu są domyślnie wyświetlane warunki płatności z konta dostawcy.       
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Metoda dostawy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście kliknij łącze w wybranym wierszu.
10. W polu Warunki dostawy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście kliknij łącze w wybranym wierszu.

## <a name="confirm-and-activate-the-agreement"></a>Potwierdzanie i aktywacja umowy
1. W okienku akcji kliknij pozycję Umowa zakupu.
2. Kliknij opcję Potwierdzenie.
    * W opcji Oznaczenie umowy jako obowiązującej zaznacz wartość Tak.  
3. Kliknij przycisk OK.
4. W okienku akcji kliknij pozycję Umowa zakupu.
5. Kliknij opcję Potwierdzenia umowy zakupu.
    * Opcja Podgląd/drukuj umożliwia wygenerowanie dokumentu umowy zakupu, który następnie można wydrukować lub wysłać do dostawcy. Jeśli później zaktualizujesz umowę i ponownie ją potwierdzisz, obie wersje będą wyświetlane w tym miejscu.  
6. Zamknij stronę.

