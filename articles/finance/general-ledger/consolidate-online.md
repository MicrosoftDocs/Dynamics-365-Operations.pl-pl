---
title: Konsolidacje finansowe online
description: W tym artykule opisano funkcje konsolidacji finansowych online dostępne w księdze głównej.
author: aprilolson
ms.date: 12/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 5843ac78adf32e738d9882c7f4e9e04a79200700
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838287"
---
# <a name="online-financial-consolidations"></a>Konsolidacje finansowe online

[!include [banner](../includes/banner.md)]

W tym artykule opisano funkcje konsolidacji finansowych online dostępne w księdze głównej. Przed przeczytaniem tego artykułu należy koniecznie przeczytać artykuł [Omówienie konsolidacji finansowych i przeliczania walut](financial-consolidations-currency-translation.md).

Po ukończeniu konfigurowania wprowadź informacje o konsolidacji na stronie **Konsolidacja [Online]**. Po zakończeniu można kliknąć przycisk **OK** lub **Zadanie wsadowe**, aby wykonać przetwarzanie konsolidacji.

## <a name="criteria"></a>Kryterium
Na karcie **Kryteria** na stronie **Konsolidacja [Online]** zdefiniuj konta, okresy i typ konsolidowanych danych.

![Karta Kryteria.](./media/criteria-consolidate-online.png "Karta Kryteria")

Poniżej znajduje się objaśnienie różnych pól umieszczonych na tej stronie:

- **Opis** — służy do wprowadzania precyzyjnego opisu konsolidowanego okresu.
- **Konto główne** — pola w tej sekcji służą do definiowania kont głównych, które będą przetwarzane.

    - **Od** i **Do** — określ zakres kont, które mają być przetwarzane. Jeśli te pola pozostaną puste, wszystkie konta ze wszystkich firm zostaną przeniesione do konsolidowanej firmy. W związku z tym jeśli konsolidujesz cztery firmy, a każda firma ma inny plan kont, wszystkie konta ze wszystkich czterech firm zostaną utworzone w konsolidowanej firmie.
    - **Użyj konta konsolidacji** — po ustawieniu tej opcji na **Tak** staje się dostępne pole **Wybierz konto konsolidacji z**. W tym polu należy określić, czy wszystkie konta mają być konsolidowane na koncie konsolidacyjnym ustawionym na stronie **Konta główne**, czy też chcesz wybrać konto w jednej z grup kont konsolidacyjnych.
    - **Grupa kont konsolidacji** — umożliwia wybór grupy, która zostanie użyta w celu zamapowania konta głównego w konsolidacji.

- **Okres konsolidacji** — pola w tej sekcji służą do definiowania okresu konsolidacji.

    - **Od** i **Do** — umożliwia określenie zakresu dat konsolidacji. Jeśli te pola pozostaną puste, konsolidacja będzie przetwarzana dla wszystkich okresów zdefiniowanych w kalendarzu księgi dla firmy. Zalecane jest niepozostawianie tych pól pustych.
    - **Wybierz kwotę konsolidacyjną z** – W tym polu określ, czy do aktualizacji kwot w walucie księgowej firmy konsolidującej zostaną użyte kwoty w walucie księgowej czy w walucie sprawozdawczej ze spółek źródłowych.

        - Wybierz **Waluta księgowa**, aby użyć kwot w walucie księgowej z firm źródłowych do aktualizacji kwot w walucie księgowej w firmie konsolidującej. Gdy ta wartość jest zaznaczona, użyj pola **Waluta księgowa konsolidacji**, aby określić, jak będą obliczane waluty księgowe w firmie konsolidującej.
        - Wybierz **Waluta sprawozdawcza**, aby użyć kwot w walucie sprawozdawczej z firm źródłowych do aktualizacji kwot w walucie księgowej w firmie konsolidującej.

            - Jeśli waluta sprawozdawcza firmy źródłowej jest taka sama jak waluta księgowa firmy konsolidującej, kwoty w walucie sprawozdawczej są kopiowane z firmy źródłowej do firmy konsolidującej.
            - Jeśli waluta sprawozdawcza firmy źródłowej różni się od waluty księgowej firmy konsolidującej, wartości są przeliczane przy użyciu informacji o wymianie, które są zdefiniowane w zakładce **Przeliczenie walut** na tej stronie, aby obliczyć wartości firmy konsolidującej.

    - **Waluta księgowa konsolidacji** – To pole jest dostępne tylko wtedy, gdy pole **Wybierz kwotę konsolidacji od** jest ustawione na **Waluta księgowania**. Określa, czy kwoty w walucie obrachunkowej z firm źródłowych są przeliczane po kursie wymiany, czy kopiowane do firmy konsolidującej. Wybierz **Użyj przeliczenia walut**, aby do obliczania sald księgowości konsolidacyjnej użyć informacji o kursach wymiany zdefiniowanych na karci **Przeliczenie walut**. Wybierz **Użyj kwoty waluty księgowej**, aby skopiować kwoty waluty księgowej z firm źródłowych do firmy konsolidującej.

        - Jeśli waluta księgowa firmy źródłowej jest taka sama jak waluta księgowa firmy konsolidującej, kwoty walutowe są kopiowane z firmy źródłowej do firmy konsolidującej.
        - Jeśli waluta księgowa firmy źródłowej różni się od waluty księgowej firmy konsolidującej, wartości są przeliczane przy użyciu informacji o wymianie, które są zdefiniowane na karcie **Przeliczenie walut** w celu obliczenia wartości firmy konsolidującej.

    - **Uwzględnij kwoty rzeczywiste** — ustaw tę opcję na **Tak**, aby konsolidować dane rzeczywiste.
    - **Uwzględnij kwoty budżetu** — ustaw tę opcję na **Tak**, aby konsolidować dane z rejestru budżetu.
    - **Przebudowa sald w trakcie konsolidacji** — nie zaleca się ustawiania tej opcji na **Tak**. Zamiast tego salda należy odbudowywać jako osobne zadanie wsadowe.

- **Modele budżetu** — jeśli wybrano konsolidowanie danych budżetu, pola w tej sekcji służą do definiowania modeli budżetu.

    - **Od** i **Do** — określ zakres modeli, które mają być używane.
    - **Typ kursu budżetowego** — umożliwia wybór typu kursu budżetowego, który ma być używany w przeliczaniu walut w danych budżetu.

## <a name="financial-dimensions"></a>Wymiary finansowe
Na karcie **Wymiary finansowe** określ wymiary, które mają być uwzględniane w konsolidowanej firmie. Aby wybrać wymiar, należy ustawić w polu **Specyfikacja** wartość **Wymiar**, a następnie określić kolejność wymiarów w konsolidowanej firmie.

![Karta wymiary finansowe.](./media/financial-dimensions-cons.png "Karta wymiary finansowe")

Bez względu na zdefiniowaną kolejność zawsze pierwszym segmentem jest **Konto główne**.

## <a name="legal-entities"></a>Firmy
Na karcie **Firmy** określ firmy, które mają być uwzględniane w konsolidowanej firmie. Można także zdefiniować procentowy udział własności w tych firmach. Jeśli określisz udział własnościowy niższy niż 100 procent, ta wartość zostanie skumulowana do konsolidowanej firmy. Dla wszelkich rozbieżności przeliczania pole **Typ konta rozbieżności konwersji** służy do wybierania konta głównego z konfiguracji na stronie **Konta dla transakcji automatycznych**.

![Karta firm.](./media/legal-entities-cons.png "Karta firm")

![Strona Konta dla transakcji automatycznych.](./media/accounts-for-automatic-cons.png "Strona Konta dla transakcji automatycznych")

## <a name="elimination"></a>Eliminacja
Na karcie **Eliminacja** masz trzy opcje przetwarzania eliminacji:

- Wybierz regułę eliminacji, a następnie w polu **Opcje propozycji** zaznacz opcję **Tylko propozycja**. Ta opcja spowoduje przetwarzanie eliminacji w procesie konsolidacji, ale nie wszystkie zdarzenia zostaną zaksięgowane w jednym kroku. Arkusz można zaksięgować później.
- Wybierz regułę eliminacji, a następnie w polu **Opcje propozycji** zaznacz opcję **Tylko księgowanie**. Ta opcja spowoduje przetwarzanie eliminacji w procesie konsolidacji i wszystkie zdarzenia zostaną zaksięgowane w jednym kroku.
- Korzystając z arkusza eliminacji, można wygenerować propozycję eliminacji niezależnie od procesu konsolidacji.

![Karta Eliminacja.](./media/elimination-cons-onl.png "Karta Eliminacja")

Aby uzyskać więcej informacji o eliminacjach, zobacz [Reguły eliminacji](./elimination-rules.md).

## <a name="currency-translation"></a>Tłumaczenie waluty
Na karcie **Przeliczanie walut** zdefiniuj firmę, konto, typ kursu wymiany i kurs wymiany. Jeśli firma konsolidująca jest przypisana do innych kont głównych niż firma źródłowa, w polach **data od** i **data do** należy wpisać konto główne firmy konsolidującej, a nie konto główne firmy źródłowej. Dla każdego wiersza encji prawnej i kont głównych w polu **Zastosuj kurs wymiany z** dostępne są trzy opcje:

- **Data konsolidacji** – Data określona w polu **Okres konsolidacji do** na zakładce **Kryteria** dla konsolidacji zostanie użyta do uzyskania kursu wymiany. Jest to kurs kasowy lub z końca miesiąca. Zobaczysz podgląd kursu, ale nie można go edytować.
- **Data transakcji** — data każdej transakcji będzie używana do wybrania kursu wymiany. Ta opcja jest najczęściej używana dla środków trwałych, a kurs często nazywa się „kursem historycznym”. Nie zobaczysz podglądu kursu, ponieważ będzie wiele kursów dla różnych transakcji w zakresie kont.
- **Kurs zdefiniowany przez użytkownika** — po wybraniu tej opcji można wprowadzić dowolny kurs wymiany. Opcja może być przydatna dla średnich kursów wymiany lub jeśli konsolidujesz na podstawie stałego kursu wymiany.

![Karta Typ przeliczania waluty.](./media/currency-translation-cons-online.png "Karta Typ przeliczania waluty")

## <a name="additional-resources"></a>Dodatkowe zasoby

Aby uzyskać więcej informacji o konsolidacjach i przeliczaniu walut, zobacz artykuł nadrzędny tego artykułu — [Omówienie konsolidacji finansowych i przeliczania walut](./financial-consolidations-currency-translation.md).

Aby uzyskać informacje o scenariuszach, w których mogą być tworzone skonsolidowane sprawozdania finansowe, zobacz [Generowanie skonsolidowanych sprawozdań finansowych](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
