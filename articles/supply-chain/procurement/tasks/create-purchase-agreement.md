---
title: Tworzenie umowy zakupu
description: Ten temat przeprowadzi Cię przez proces tworzenia umowy zakupu.
author: mkirknel
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec792ca27bf0245ff25e59cfe28122f17caec7fc
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2019
ms.locfileid: "1866857"
---
# <a name="create-a-purchase-agreement"></a>Tworzenie umowy zakupu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ten temat przeprowadzi Cię przez proces tworzenia umowy zakupu. Zazwyczaj robi to kierownik ds. zakupów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem trzeba mieć skonfigurowaną klasyfikacji umów zakupu. Po utworzeniu umowy można jej używać podczas tworzenia zamówienia zakupu. Spowoduje to skopiowanie warunków umowy do nagłówka oraz do wszystkich wierszy w zamówieniu, których dotyczy umowa.


## <a name="create-a-new-purchase-agreement"></a>Tworzenie nowej umowy zakupu
1. Wybierz kolejno **Okienko nawigacji> Moduły > Zaopatrzenie i sourcing > Umowy zakupu > Umowy zakupu**.
2. Kliknij przycisk **Nowy**.
3. W polu **Konto dostawcy** wybierz wiersz z żądanym rekordem z menu rozwijanego.
4. W polu **Klasyfikacja umowy zakupu** wybierz wiersz z żądanym rekordem z menu rozwijanego.
5. Rozwiń skróconą kartę **Ogólne**.
6. W polu **Data wygaśnięcia** wprowadź datę.

    - Ta data ważności będzie domyślna dla wszystkich wierszy zobowiązań i określi, jak długo każde konkretne zobowiązanie jest ważne.  

7. W polu **Tytuł dokumentu** nadaj nazwę umowie zakupu.

    - Pozostaw w polu **Domyślne zobowiązanie** wartość **Zobowiązanie co do ilości produktu** (lub ją zmień na tą, jeśli jest ustawiona inna).  
    - Domyślna wartość zobowiązania określa opcje dostępne w wierszach umowy. Jeśli przy tworzeniu wierszy umowy potrzebujesz nowego typu zobowiązania, należy zmienić domyślne zobowiązanie w nagłówku. Istnieją 4 rodzaje zobowiązań: **Zobowiązanie co do ilości produktu** — na określoną ilość produktu; **Zobowiązanie co do wartości produktu** — na określoną wartość produktu w walucie; **Zobowiązanie co do wartości w ramach kategorii produktu** — na wartość produktu w określonej walucie w kategorii zaopatrzenia, gdzie kwota może dotyczyć towaru z katalogu lub spoza katalogu; **Zobowiązanie co do wartości** — na określoną kwocie w walucie, która może być pokryta przez jakikolwiek produkt z dowolnej kategorii zaopatrzenia.  

8. Kliknij przycisk **OK**.

## <a name="add-a-commitment"></a>Dodawanie zobowiązania
1. Wybierz **Dodaj wiersz**.
2. W polu **Numer produktu** wybierz odpowiedni rekord z menu listy rozwijanej.
3. W polu **Ilość** wpisz liczbę. Jest to ilość całkowita, jaką zgodzono się kupić od dostawcy.  
4. W polu **Cena jednostkowa** wpisz liczbę.
5. Rozwiń sekcję **Szczegóły wiersza**.
6. W opcji **Wymuszono maks**. zaznacz wartość **Tak**. Opcja **Wymuszono maks.** ogranicza użycie zobowiązania. Można kupować tylko do ilości określonej w polu **Ilość** dla wiersza.  

## <a name="add-header-conditions"></a>Dodawanie warunków nagłówka
1. W okienku akcji kliknij pozycję **Opcje**.
2. Wybierz **Zmień widok**.
3. Wybierz **Widok nagłówka**.
4. Rozwiń sekcję **Warunki**.
5. W polu **Metoda płatności** wybierz odpowiedni rekord z menu rozwijanego. W tym miejscu są domyślnie wyświetlane warunki płatności z konta dostawcy.  
6. W polu **Metoda dostawy** wybierz odpowiedni rekord z menu rozwijanego.
7. W polu **Warunki dostawy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.

## <a name="confirm-and-activate-the-agreement"></a>Potwierdzanie i aktywacja umowy
1. W okienku akcji kliknij pozycję **Umowa zakupu**.
2. Wybierz **Potwierdzenie**. W opcji **Oznaczenie umowy jako obowiązującej** zaznacz wartość **Tak**.  
3. Kliknij przycisk **OK**.
4. W okienku akcji kliknij pozycję **Umowa zakupu**.
5. Wybierz **Potwierdzenia umowy zakupu**. Opcja **Podgląd/drukuj** umożliwia wygenerowanie dokumentu umowy zakupu, który następnie można wydrukować lub wysłać do dostawcy. Jeśli później zaktualizujesz umowę i ponownie ją potwierdzisz, obie wersje będą wyświetlane w tym miejscu.  
6. Zamknij stronę.

