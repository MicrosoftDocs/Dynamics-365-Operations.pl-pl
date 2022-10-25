---
title: Importowanie i eksportowanie obliczeń podatku
description: Ten artykuł zawiera informacje dotyczące funkcji importu i eksportu w usłudze obliczania podatku.
author: Kai-Cloud
ms.date: 10/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8666d4971e36279ebd2b1396de7cab37680980e6
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690241"
---
# <a name="import-and-export-tax-calculations"></a>Importowanie i eksportowanie obliczeń podatku

Ten artykuł zawiera informacje dotyczące funkcji importu i eksportu w usłudze obliczania podatku. Ta funkcja pomaga w elastycznej i efektywnej konfiguracji.

## <a name="import-and-export-tax-codes"></a>Importowanie i eksportowanie kodów podatków

### <a name="export-templates"></a>Eksportowanie szablonów

1. Zaloguj się do usługi [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. W obszarze roboczym **Funkcje globalizacji**, wybierz opcję **Funkcje**, a następnie wybierz kafelek **Obliczanie podatku**.
3. Wybierz istniejącą funkcję lub [utwórz nową funkcję](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. W siatce **Wersje** wybierz pozycję **Edytuj**.
5. Na stronie funkcji **Obliczanie podatku** ustaw [wersję konfiguracji](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Na karcie **Kody podatków** wybierz pozycję **Import**.
7. Wybierz opcję **Eksportuj szablon kodu podatku**, aby pobrać plik **TaxCodesTemplate.zip**.
8. Rozpakuj plik **TaxCodesTemplate.zip**. Szablony kodów podatków są kompresowane oddzielnie zgodnie z wartością **Źródło obliczenia**.
9. Rozpakuj plik **By Net Amount.zip**, aby uzyskać następujące pliki z wartościami rozdzielanymi przecinkami (CSV):

    - **TaxCode.csv** — wprowadź kody podatków.
    - **TaxLimit.csv** — wprowadź limity podatkowe dla każdego kodu podatku.
    - **TaxRate.csv** — wprowadź stawki podatkowe dla każdego kodu podatku.

> [!NOTE]
> Domyślnie wpisy dla kodu podatku **Przykład** są dostępne w szablonach. Jeśli kod podatku **Przykład** nie zostanie usunięty z plików CSV, zostanie zaimportowany do tej funkcji.

### <a name="import-tax-codes"></a>Importowanie kodów podatków

Aby zaimportować kod podatku **Przykład** z szablonu do funkcji obliczania podatku, wykonaj następujące kroki.

1. W usłudze RCS, na stronie funkcji **Obliczanie podatku**, na karcie **Kody podatków** wybierz pozycję **Importuj**.
2. Wybierz przycisk **Przeglądaj**, znajdź i wybierz plik **TaxCode.csv**, a następnie w polu **Tabela docelowa** wybierz opcję **Kod podatku**.
3. Wybierz przycisk **OK**, aby zaimportować kod podatku.
4. Znajdź i wybierz plik **TaxRate.csv**, a następnie w polu **Tabela docelowa** wybierz opcję **Stawka podatku**.
5. Wybierz przycisk **OK**, aby zaimportować stawkę podatku.
6. Znajdź i wybierz plik **TaxLimit.csv**, a następnie w polu **Tabela docelowa** wybierz opcję **Limit podatku**.
7. Wybierz przycisk **OK**, aby zaimportować limit podatku.

Można także bezpośrednio zaimportować plik ZIP, który zawiera wszystkie trzy pliki CSV. Dzięki temu import będzie można wykonać szybko i łatwo.

1. W usłudze RCS, na stronie funkcji **Obliczanie podatku**, na karcie **Kody podatków** wybierz pozycję **Importuj**.
2. Wybierz przycisk **Przeglądaj**, znajdź i wybierz plik **By Net Amount.zip**, a następnie wybierz przycisk **OK**.

### <a name="export-tax-codes"></a>Eksportowanie kodów podatków

1. W usłudze RCS, na stronie funkcji **Obliczanie podatku**, na karcie **Kody podatków** wybierz pozycję **Eksportuj**.

    Przycisk **Eksportuj** jest dostępny, jeśli w siatce **Kody podatków** znajduje się co najmniej jeden kod podatku.

2. Wybierz przycisk **OK**, aby wyeksportować wszystkie kody podatków funkcji w pliku ZIP.

> [!NOTE]
> Eksportowany plik będzie szablonem do importowania kodów podatków do odpowiedniej funkcji.

## <a name="import-and-export-applicability-rules"></a>Importowanie i eksportowanie reguł zastosowania

### <a name="export-applicability-rules"></a>Eksportowanie reguł zastosowania

1. Zaloguj się w [RCS](https://marketing.configure.global.dynamics.com/).
2. W obszarze roboczym **Funkcje globalizacji**, wybierz opcję **Funkcje**, a następnie wybierz kafelek **Obliczanie podatku**.
3. Wybierz istniejącą funkcję lub [utwórz nową funkcję](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. W siatce **Wersje** wybierz pozycję **Edytuj**.
5. Na stronie funkcji **Obliczanie podatku** ustaw [wersję konfiguracji](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Na karcie **Stosowanie grupy podatków** zaznacz wiersze w siatce **Ustaw stosowanie grupy podatków**.
7. Wybierz przycisk **Otwórz w pakiecie Microsoft Office**, a następnie opcję **Dynamiczna macierz stosowania usługi**.

    [![Eksportowanie reguł zastosowania do programu Microsoft Excel na stronie funkcji Obliczanie podatku.](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. Wybierz przycisk **Pobierz**, aby wyeksportować wybrane wiersze do arkusza programu Microsoft Excel.

### <a name="import-applicability-rules"></a>Importowanie reguł zastosowania

Pobrany arkusz programu Excel zawiera strukturę siatki **Konfigurowanie zastosowania grupy podatków**. Nowe reguły można dodawać bezpośrednio w arkuszu. Po zakończeniu wykonaj następujące kroki, aby zaimportować nowe reguły z powrotem do siatki **Konfigurowanie zastosowania grupy podatków**.

1. W arkuszu programu Excel wybierz i skopiuj wiersze do zaimportowania.
2. W usłudze RCS, na stronie funkcji **Obliczanie podatku** na karcie **Stosowanie grupy podatków** wybierz opcję **Dodaj**, aby wstawić pusty rekord u dołu siatki **Konfigurowanie zastosowanie grupy podatków**.
3. Naciśnij klawisze **Ctrl+V**, aby wkleić skopiowane wiersze do siatki.
4. Wybierz opcję **Zapisz**.

## <a name="import-feature-demo-data"></a>Importowanie dane pokazowych funkcji

Aby zaimportować dane pokazowe funkcji, należy wykonać następujące kroki.

1. Zaloguj się w [RCS](https://marketing.configure.global.dynamics.com/).
2. W obszarze roboczym **Funkcje globalizacji**, wybierz opcję **Funkcje**, a następnie wybierz kafelek **Obliczanie podatku**.
3. Wybierz pozycję **Importuj**, a następnie na stronie **Importowanie funkcji z repozytorium globalnego** wybierz pozycję **Synchronizuj**. 
4. W tabeli wybierz funkcję **tax-calculation-feature-demo-data**, a następnie wybierz pozycję **Importuj**.
5. Wybierz pozycję **Wyświetl**, aby przejrzeć kody, grupy i reguły możliwości zastosowania podatków zdefiniowane w zaimportowanej funkcji.
6. W aplikacji Finance przejdź do osoby prawnej **DEMF**, a następnie przejdź do pozycji **Podatki** \> **Konfiguracja** \> **Konfiguracja podatkowa** \> **Parametry obliczeń podatkowych**.
7. Na karcie **Ogólne** wybierz opcję **Włącz usługę obliczania podatku**.
8. W polu **Nazwa konfiguracji funkcji** wybierz opcję **tax-calculation-feature-demo-data**.
9. Wybierz **okres rozliczeniowy** i **grupę księgowania** dla nowych pokazowych kodów podatku, a następnie wybierz pozycję **Potwierdź**.
10. Wybierz opcję **Zapisz**.

> [!NOTE]
> Funkcja pokazowa **tax-calculation-feature-demo-data** opiera się na wersji funkcji **40.54.234** i została zaprojektowana pokazowej osoby prawnej **DEMF**. Upewnij się, że aplikacja Finance i usługa RCS zostały uaktualnione do wersji 10.0.26 lub nowszej.
