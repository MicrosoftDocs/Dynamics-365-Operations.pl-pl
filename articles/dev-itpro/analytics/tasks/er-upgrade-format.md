--- 
title: "Uaktualnianie formatów poprzez zastosowanie nowych wersji podstawowych"
description: "W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zarządzać konfiguracją formatu raportowania elektronicznego (ER)."
author: NickSelin
manager: AnnBe
ms.date: 02/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 7a14299c3bdcc33a4441d1cc096b198af4d4ae4c
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="upgrade-formats-by-adopting-new-base-versions"></a>Uaktualnianie formatów poprzez zastosowanie nowych wersji podstawowych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zarządzać konfiguracją formatu raportowania elektronicznego (ER). W tej procedurze pokazano sposób tworzenia niestandardowej wersji formatu w oparciu o format otrzymany od dostawcy konfiguracji (CP). Ponadto wyjaśniono, jak zastosować nową bazową wersję tego formatu.



Przed wykonaniem tych kroków należy najpierw wykonać procedury „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego” i „Używanie utworzonego formatu do generowania elektronicznych dokumentów płatności”. Kroki można wykonać na danych firmy GBSI.


## <a name="select-format-configuration-for-customization"></a>Wybór konfiguracji formatu do dostosowania
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * W tym przykładzie przykładowa firma Litware, Inc. (`http://www.litware.com`) będzie pełniła rolę dostawcy konfiguracji, który obsługuje konfiguracje formatów płatności elektronicznych dla określonego kraju.  Przykładowa firma Proseware, Inc. (`http://www.proseware.com`) będzie pełniła rolę użytkownika konfiguracji formatu dostarczonej przez firmę Litware, Inc. Firma Proseware, Inc. będzie używać tych formatów w niektórych regionach tego kraju.  
2. Kliknij opcję Konfiguracje raportowania.
3. Kliknij przycisk Pokaż filtry.
4. Zastosuj następujące filtry: w polu „Nazwa” wprowadź wartość filtru „BACS (fikcyjny brytyjski)”, używając operatora filtru „zaczyna się od”.
    * BACS (fikcyjny brytyjski)  
    * Wybrana konfiguracja formatu BACS (fikcyjny brytyjski) jest własnością dostawcy Litware, Inc.  
5. Kliknij przycisk Pokaż filtry.
6. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wersja formatu o stanie Zakończono będzie używana przez firmę Proseware, Inc. w celu dostosowania.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>Tworzenie nowej konfiguracji niestandardowego formatu dokumentów elektronicznych
Firma Proseware, Inc. otrzymała wersję 1.1 konfiguracji BACS (fikcyjnej brytyjskiej), która zawiera początkowy format do generowania dokumentów płatności elektronicznych, od firmy Litware, Inc. zgodnie z wykupioną subskrypcją usług. Firma Proseware, Inc. chce rozpocząć używanie tego formatu jako standardowego w swoim kraju, ale jest potrzebne pewne dostosowanie w celu obsługi specjalnych wymagań regionalnych. Firma Proseware, Inc. chce także zachować możliwość uaktualniania niestandardowego formatu natychmiast, gdy jego nowa wersja (ze zmianami uwzględniającymi nowe wymagania specyficzne dla kraju) zostanie pobrana z firmy Litware, Inc., oraz wykonywać to uaktualnienie jak najtaniej.  W tym celu firma Proseware, Inc. musi utworzyć konfigurację, używając jako bazy konfiguracji BACS (fikcyjnej brytyjskiej) otrzymanej od firmy Litware, Inc.  
1. Zamknij stronę.
2. Wybierz firmę Proseware, Inc., aby ustawić ją jako aktywnego dostawcę.
3. Kliknij opcję Ustaw jako aktywny.
4. Kliknij opcję Konfiguracje raportowania.
5. W drzewie rozwiń węzeł „Płatności (model uproszczony)”.
6. W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.
    * Zaznacz konfigurację BACS (fikcyjną brytyjską) firmy Litware, Inc. Firma Proseware, Inc. użyje wersji 1.1 jako bazy dla niestandardowej wersji.  
7. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
    * Pozwoli to utworzyć nową konfigurację dla niestandardowego formatu płatności.  
8. W polu Nowy wpisz „Pochodzi od nazwy: BACS (fikcyjny brytyjski), Litware, Inc.”.
    * Wybierz opcję Utwórz pochodne, aby potwierdzić użycie konfiguracji BACS (fikcyjnej brytyjskiej) jako bazy do utworzenia niestandardowej wersji.  
9. W polu Nazwa wpisz „BACS (niestandardowy fikcyjny brytyjski)”.
    * BACS (niestandardowy fikcyjny brytyjski)  
10. W polu Opis wpisz „Płatność dla dostawcy BACS (niestandardowy fikcyjny brytyjski)”.
    * Płatność dla dostawcy BACS (niestandardowy fikcyjny brytyjski)  
    * Aktywny dostawca konfiguracji (firma Proseware, Inc.) jest automatycznie umieszczany w tym miejscu. Ten dostawca będzie mógł obsługiwać tę konfigurację. Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.  
11. Kliknij przycisk Utwórz konfigurację.

## <a name="customize-your-format-for-the-electronic-document"></a>Dostosowywanie formatu dokumentów elektronicznych
1. Kliknij przycisk Konstruktor.
2. Kliknij przycisk Rozwiń/zwiń.
3. Kliknij przycisk Rozwiń/zwiń.
4. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank”.
5. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
6. W drzewie zaznacz element „XML\Element”.
7. W polu Nazwa wpisz „IBAN”.
    * Numer IBAN  
8. Kliknij przycisk OK.
9. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\IBAN”.
10. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
11. W drzewie zaznacz element „Tekst\Ciąg”.
12. Kliknij przycisk OK.
13. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa\Ciąg”.
14. W polu Długość maksymalna wpisz „60”.
15. Kliknij kartę Mapowanie.
16. W drzewie rozwiń model„”
17. W drzewie rozwiń węzeł „model\Płatności”.
18. W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.
19. W drzewie rozwiń „model\Płatności\Konto wierzyciela".
20. W drzewie zaznacz element „model\Płatności\Wierzyciel\Konto\IBAN”.
21. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar = model.Płatności\Dostawca\Bank\IBAN\Ciąg”.
22. Kliknij opcję Powiąż.
23. Kliknij przycisk Zapisz.

## <a name="validate-the-customized-format"></a>Sprawdzanie poprawności formatu niestandardowego
1. Kliknij przycisk Sprawdź poprawność.
    * Sprawdź poprawność modyfikacji układu i mapowań danych dostosowanego formatu niestandardowego, aby się upewnić, że wszystkie powiązania działają poprawnie.  
2. Zamknij stronę.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>Zmiana stanu bieżącej wersji niestandardowej konfiguracji formatu
    * Zmień stan żądanej konfiguracji formatu z Wersja robocza na Zakończono, aby ją udostępnić na potrzeby generowania dokumentów płatności.  
1. Kliknij przycisk Zmień stan.
    * Należy zauważyć, że bieżąca wersja wybranej konfiguracji ma stan Wersja robocza.  
2. Kliknij przycisk Wykonaj.
3. Wypełnij pole Opis.
4. Kliknij przycisk OK.
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.1.1. Oznacza to, że jest to wersja 1 niestandardowego formatu BACS (niestandardowego fikcyjnego brytyjskiego), która bazuje na wersji 1 formatu BACS (fikcyjnego brytyjskiego), który z kolei jest oparty na wersji 1 modelu danych Płatności (modelu uproszczonego).  

## <a name="test-the-customized-format-to-generate-payment-files"></a>Testowanie niestandardowego formatu generowania plików płatności
W równoległej sesji programu Dynamics 365 for Finance and Operations wykonaj procedurę „Używanie utworzonego formatu do generowania elektronicznych dokumentów płatności”. W parametrach metody płatności elektronicznych wybierz format BACS (niestandardowy fikcyjny brytyjski). Upewnij się, że utworzony plik płatności zawiera ostatnio wprowadzony węzeł XML przedstawiający kod IBAN zgodnie wymogami regionalnymi.  

## <a name="update-the-existing-country-specific-configuration"></a>Aktualizowanie istniejącej konfiguracji specyficznej dla kraju
Firma Litware, Inc. musi zaktualizować konfigurację BACS (niestandardową fikcyjną brytyjską) i dostosować ją do nowych wymagań krajowych dotyczących zarządzania formatem dokumentów elektronicznych. Później zmiany te zostaną zawarte w nowej wersji tej konfiguracji, który będzie oferowana subskrybentom usług, w tym firmie Proseware, Inc.  

W faktycznych procesach związanych ze świadczeniem usług każda nowa wersja konfiguracji BACS (fikcyjnej brytyjskiej) może być importowana przez firmę Proseware, Inc. z repozytorium konfiguracji firmy Litware, Inc. w usłudze LCS. W tej procedurze zasymulujemy to poprzez aktualizację konfiguracji BACS (fikcyjnej brytyjskiej) w imieniu usługodawcy.

1. Zamknij stronę.
2. Zaznacz dostawcę Litware, Inc.  
3. Kliknij opcję Ustaw jako aktywny.
4. Kliknij opcję Konfiguracje raportowania.
5. W drzewie rozwiń węzeł „Płatności (model uproszczony)”.
6. W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.
    * Wersja robocza konfiguracji BACS (fikcyjnej brytyjskiej) należąca do dostawcy Litware, Inc. została wybrana, aby wprowadzić zmiany uwzględniające nowe wymagania specyficzne dla kraju.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>Lokalizowanie bazowego formatu dokumentów elektronicznych
Załóżmy, że istnieją nowe wymagania specyficzne dla kraju, których obsługę musi zapewnić firma Litware:  
- Wypełnienie kodu SWIFT banku wierzyciela w każdej transakcji płatności.  
- Limit 100 znaków długości tekstu nazwy dostawcy w generowanym pliku.  
 
Zaznacz wersję roboczą żądanej konfiguracji, aby wprowadzić w niej wymagane zmiany.  

1. Kliknij przycisk Konstruktor.
2. Kliknij przycisk Rozwiń/zwiń.
3. Kliknij przycisk Rozwiń/zwiń.
4. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank”.
5. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
6. W drzewie zaznacz element „XML\Element”.
7. W polu Nazwa wpisz „SWIFT”.
    * SWIFT  
8. Kliknij przycisk OK.
9. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\SWIFT”.
10. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
11. W drzewie zaznacz element „Tekst\Ciąg”.
12. Kliknij przycisk OK.
13. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa\Ciąg”.
14. W polu Długość maksymalna wpisz „100”.
15. Kliknij kartę Mapowanie.
16. W drzewie rozwiń model„”
17. W drzewie rozwiń węzeł „model\Płatności”.
18. W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.
19. W drzewie rozwiń „model\Płatności\Wierzyciel\Agent".
20. W drzewie zaznacz element „model\Płatności\Wierzyciel\Agent\SWIFT”.
21. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar = model.Płatności\Dostawca\Bank\SWIFT\Ciąg”.
22. Kliknij opcję Powiąż.
23. Kliknij przycisk Zapisz.

## <a name="validate-the-localized-format"></a>Sprawdzanie poprawności zlokalizowanego formatu
1. Kliknij przycisk Sprawdź poprawność.
2. Zamknij stronę.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>Zmiana stanu bieżącej wersji konfiguracji formatu bazowego
Zmień stan zaktualizowanej konfiguracji formatu bazowego z Wersja robocza na Zakończono, aby ją udostępnić na potrzeby generowania dokumentów płatności oraz aktualizowania opartych na niej konfiguracji formatów.  
1. Kliknij przycisk Zmień stan.
    * Należy zauważyć, że bieżąca wersja wybranej konfiguracji ma stan Wersja robocza.  
2. Kliknij przycisk Wykonaj.
3. Wypełnij pole Opis.
4. Kliknij przycisk OK.
5. Na liście znajdź i zaznacz odpowiedni rekord.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>Zmiana bazowej wersji niestandardowej konfiguracji formatu
Firma Proseware, Inc. została poinformowana, że nowa wersja 1.2 konfiguracji BACS (fikcyjnej brytyjskiej) jest dostępna na potrzeby generowania elektronicznych dokumentów płatności zgodnie z niedawno ogłoszonymi wymaganiami specyficznymi dla kraju. Firma Proseware, Inc. chce zacząć używać tego formatu jako standardowego dla kraju.  W tym celu firma Proseware, Inc. musi zmienić wersję konfiguracji stanowiącą bazę dla niestandardowej konfiguracji BACS (niestandardowej fikcyjnej brytyjskiej). Zamiast wersji 1.1 konfiguracji BACS (fikcyjnej brytyjskiej) należy używać nowej wersji 1.2.  

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Wybierz dostawcę Proseware, Inc., aby oznaczyć go jako aktywnego.
3. Kliknij opcję Ustaw jako aktywny.
4. Kliknij opcję Konfiguracje raportowania.
5. W drzewie rozwiń węzeł „Płatności (model uproszczony)”.
6. W drzewie rozwiń węzeł „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.
7. W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)\BACS (niestandardowy fikcyjny brytyjski)”.
    * Zaznacz konfigurację BACS (niestandardową fikcyjną brytyjską), która jest własnością firmy Proseware, Inc.  
    * Użyj wersji roboczej wybranej konfiguracji, aby wprowadzić wymagane zmiany.  
8. Kliknij opcję Zmień bazę.
    * Zaznacz nową wersję 1.2 konfiguracji bazowej, aby zastosować ją jako nową podstawę do aktualizowania konfiguracji.  
9. Kliknij przycisk OK.
    * Należy zauważyć, że wykryto pewne konflikty między scaleniem niestandardowej wersji a nową wersją bazową. Konflikty te reprezentują niektóre zmiany formatu, których nie można scalić automatycznie.  

## <a name="resolve-rebase-conflicts"></a>Rozwiązywanie konfliktów związanych ze zmianą bazy
1. Kliknij przycisk Konstruktor.
    * Należy zauważyć, że zmiana limitu długości tekstu nazwy dostawcy nie została rozwiązana automatycznie. W związku z tym znajduje się na liście konfliktów. Dla każdego konfliktu o typie Aktualizacja są dostępne następujące opcje: - Zastosowanie poprzedniej wartości bazowej (przycisk na siatce), aby umieścić wartość z poprzedniej wersji bazowej (0 w naszym przypadku).  - Zastosowanie wartości bazowej (przycisk u góry siatki) w celu umieszczenia wartości nowej wersji bazowej (100 w naszym przypadku).  - Zachowanie własnej (niestandardowej) wartości (60 w naszym przypadku).  Kliknij przycisk Zastosuj wartość podstawową, aby stosować limit 100 znaków w długości nazwy dostawcy.  
    * Należy zwrócić uwagę, że firmy Proseware, Inc. i Litware, Inc. mają niestandardowe i lokalne wersje tego formatu wykorzystujące kody IBAN i SWIFT z powiązanymi składnikami, które są automatycznie scalane w formacie zarządzania.  
2. Kliknij opcję Zastosuj wartość podstawową.
    * Kliknij przycisk Zastosuj wartość podstawową, aby stosować limit 100 znaków specyficzny dla kraju do nazw dostawców.  
3. Kliknij przycisk Zapisz.
    * Zapisanie formatu spowoduje usunięcie rozwiązanych konfliktów z listy konfliktów.  
4. Zamknij stronę.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>Zmiana stanu nowej wersji niestandardowej konfiguracji formatu
1. Kliknij przycisk Zmień stan.
    * Zmień stan zaktualizowanej niestandardowej konfiguracji formatu z Wersja robocza na Zakończono. Spowoduje to udostępnienie konfiguracji formatu do generowania dokumentów płatności. Należy zauważyć, że bieżąca wersja wybranej konfiguracji ma stan Wersja robocza.  
2. Kliknij przycisk Wykonaj.
3. Wypełnij pole Opis.
4. Kliknij przycisk OK.
    * Należy zauważyć, że utworzona konfiguracji została zapisana jako ukończona wersja 1.2.2: wersja 2 bazowego formatu BACS (niestandardowego fikcyjnego brytyjskiego), która bazuje na wersji 2 formatu BACS (fikcyjnego brytyjskiego), który z kolei jest oparty na wersji 1 modelu danych Płatności (modelu uproszczonego).  

## <a name="test-the-customized-format-for-payment-files-generation"></a>Testowanie niestandardowego formatu generowania plików płatności
W równoległej sesji programu Dynamics 365 for Finance and Operations wykonaj procedurę „Używanie utworzonego formatu do generowania elektronicznych dokumentów płatności”. W parametrach metody płatności elektronicznych wybierz utworzony format „BACS (niestandardowy fikcyjny brytyjski)”. Upewnij się, że utworzony plik płatności zawiera ostatnio wprowadzony przez firmę Proseware, Inc. węzeł XML przedstawiający kod konta IBAN zgodnie wymogami regionalnymi. Plik powinien również zawierać ostatnio wprowadzony przez firmę Litware, Inc. węzeł XML przedstawiający kod banku SWIFT zgodnie wymogami krajowymi.  


