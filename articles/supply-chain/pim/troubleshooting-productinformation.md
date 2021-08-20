---
title: Rozwiązywanie problemów z informacjami o produktach
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z informacjami o produktach.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5b74c1a769b3f0c3b848a034ed3d1bab76fda7eb5d8d62f4b3608d8706c696dc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778657"
---
# <a name="troubleshoot-product-information"></a>Rozwiązywanie problemów z informacjami o produktach

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z informacjami o produktach.

## <a name="i-cant-delete-a-released-product"></a>Nie można usunąć zwolnionego produktu.

### <a name="issue-description"></a>Opis problemu

Zwolniony produkt i wszystkie jego warianty można usunąć tylko w przypadku, gdy zwolniony produkt nie ma żadnych powiązanych transakcji.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby usunąć zwolniony produkt lub produkt główny, należy wykonać następujące kroki.

1. Zamknij wszystkie otwarte transakcji dla towarów.
1. Zmniejsz ilość zapasów do 0 (zera).
1. Przeprowadź zamknięcie zapasów.
1. Usuń wszystkie warianty produktu dla produktu głównego, który chcesz usunąć.

## <a name="can-i-change-the-item-number-of-a-released-product"></a>Czy można zmienić numer pozycji dla zwolnionego produktu?

W większości przypadków nie można edytować numerów pozycji zwolnionych produktów, ponieważ ta zmiana spowoduje uszkodzenie danych. Numer pozycji można edytować tylko wtedy, gdy konieczne jest naprawienie uszkodzeń danych spowodowanych przez poprzednią zmianę nazwy klucza podstawowego wydanego produktu, jak wspomniano na liście [usuniętych lub przestarzałych funkcji Finance and Operations 10.0.0 z aktualizacją Platform update 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).

Jeśli chcesz mieć możliwość edytowania numerów pozycji dla zwolnionych produktów, [zagłosuj na ten pomysł w portalu pomysłów](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a>Domyślna reguła usuwania z produktu nie jest wprowadzana w wierszu listy składowej.

### <a name="issue-description"></a>Opis problemu

Po dodaniu pozycji do wiersza listy składowej (BOM) system nie korzysta z domyślnej reguły usuwania ustawionej dla pozycji. Innymi słowy, reguła usuwania z pozycji nie jest wyświetlana na stronie **wiersza BOM**.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jeśli w wierszu BOM określono regułę usuwania, będzie ona dotyczyć tego wiersza BOM. Jeśli jednak reguła usuwania jest pusta lub jeśli nie została ustawiona w wierszu BOM, reguła usuwania, która jest ustawiona dla pozycji, będzie nadal stosowana do tego wiersza BOM, nawet jeśli nie jest wyświetlana w wierszu BOM.

Domyślna logika dla innych funkcji w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management nie działa zwykle w ten sposób. Nie można jednak zmienić bieżącego zachowania. W przeciwnym razie niektóre istniejące dostosowania zależne od niego mogą zostać uszkodzone.

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a>System umożliwia zapisywanie duplikatów kodów kreskowych dla różnych towarów lub dla tego samego towaru o różnych wymiarach.

System nie wymusza obecnie unikatowych kodów kreskowych, a dodanie tego ograniczenia spowodowałoby zmianę powodującą niezgodność. W rzeczywistości Microsoft ma dowody na to, że niektóre istniejące instalacje klientów zostałyby uszkodzone przez tę zmianę. Jednak w przyszłości będzie rozważana zmiana projektu umożliwiająca włączenie tej funkcji.

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a>Podczas edytowania szablonów rekordów pozycji zgłaszany jest następujący komunikat o błędzie: „Nie można utworzyć lokalizacji magazynu, ponieważ pozycja nie jest magazynowana. W przypadku pozycji magazynowych należy wybrać opcję produktu magazynowego w grupie modeli skojarzonej pozycji”.

### <a name="issue-description"></a>Opis problemu

Ten problem występuje w przypadku wykonania tych kroków w celu utworzenia szablonu dla towaru, który nie jest magazynowany.

1. Umożliwia otwarcie zwolnionego produktu, który nie jest magazynowany.
1. W okienku akcji na karcie **Opcje** wybierz opcję **Informacje o rekordzie**.
1. W oknie dialogowym **Informacje o rekordzie** wybierz pozycję **Szablon kont firmy**.

W takim przypadku zostanie wyświetlony następujący komunikat o błędzie:

> Nie można utworzyć lokalizacji magazynu, ponieważ pozycja nie jest magazynowana. W przypadku pozycji magazynowych należy wybrać opcję produktu magazynowego w grupie modeli skojarzonej pozycji.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Proces tworzenia szablonów produktów wymaga użycia dodatkowej logiki specyficznej dla produktu. Z tego względu nie można w tym celu wybrać ogólnego przycisku **Szablon kont firmy**. Zamiast tego należy wykonać następujące kroki.

1. Otwórz zwolniony produkt.
1. W okienku akcji, na karcie **Produkt**, w grupie **Nowy** wybierz **Szablon \> Utwórz udostępniony szablon**.

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a>Domyślny tekst pomoc dodawany w atrybutach produktu nie został wprowadzony w zwolnionym produkcie.

Opis i tekst pomocy dodane w atrybutach produktu nie są domyślnie widoczne lub wprowadzane w zwolnionych produktach. Jest to celowe.

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a>Domyślna ilość, która jest wprowadzana, różni się pod względem rejestracji z BOM i gdy jest rejestrowana z wersji BOM.

### <a name="issue-description"></a>Opis problemu

Domyślnie podczas dodawania pozycji do BOM ilość jest ustawiana na 1 zamiast ilości zdefiniowanej w polu **Min. ilość zamówiona** na stronie **Ustawienia domyślne zamówienia** dla wybranego produktu. Jednak po dodaniu pozycji z wersji BOM i wybraniu pozycji i wariantu ilość, która została wprowadzona domyślnie, uwzględnia minimalną ilość ustawioną w domyślnych ustawieniach zamówienia dla określonych wymiarów.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

To zachowanie jest oczekiwane. Jednak fakt, że logika różni się w BOM i w wersji BOM jest znanym problemem. Jednak to zachowanie nie zostanie zmienione, ponieważ zmiana może mieć wpływ na wiele różnych scenariuszy klientów.

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a>W szczegółach zwolnionego produktu nie mogę zmienić dołączonych obrazów przekazanych z jednostki danych załączników do dokumentu produktu.

### <a name="issue-description"></a>Opis problemu

Ten problem może wystąpić podczas dołączania obrazu do pozycji przy użyciu jednostki danych *Załączniki do dokumentu produktu*. W takim przypadku obraz pozycji jest wyświetlany dla pozycji. Jeśli jednak zostanie wybrana opcja **Zmień obraz**, na liście przekazanych obrazów nic nie będzie widoczne. Ponadto nie są pokazywane żadne załączniki dla pozycji.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jednostka *EcoResProductDocumentAttachmentEntity* (*Załączniki do dokumentu produktu*) importuje załączniki dokumentów dla *produktów*, ale nie dla *zwolnionych produktów*. (Zwolnione produkty są również nazywane *pozycjami*.) Aby wyświetlić załączniki dla pozycji na stronie **Szczegóły zwolnionego produktu**, należy użyć opcji *Jednostka EcoResReleasedProductDocumentAttachmentEntity* (*Załączniki do dokumentu zwolnionego produktu*).

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a>Łącznik Microsoft Flow zawiera następujący komunikat o błędzie: „Aktualizacja jest niedozwolona dla pola ProductNumber”.

### <a name="issue-description"></a>Opis problemu

Ten problem występuje w przypadku próby zaktualizowania pola **Numer produktu** przy użyciu jednostki *Zwolnione produkty* w wersji V2 i Microsoft Flow.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

To zachowanie jest oczekiwane. Możliwość edytowania numeru produktu dla zwolnionego produktu została usunięta w Dynamics 365 Finance and Operations 10.0.0 z aktualizacją Platform update 24, aby ułatwić zapobieganie uszkodzeniu danych. W wyjątkowych przypadkach, jeśli trzeba naprawić uszkodzenie danych spowodowane przez poprzednią nazwę klucza podstawowego zwolnionego produktu, można skontaktować się z pomocą techniczną firmy Microsoft, aby zażądać tymczasowego usunięcia tego ograniczenia.

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a>Nie można utworzyć wariantu zwolnionego produktu w innej osobie prawnej.

### <a name="issue-description"></a>Opis problemu

Jeśli użytkownik spróbuje zwolnić produkt główny bez wariantów, a następnie utworzy warianty w poszczególnych osobach prawnych (firmach) zgodnie z wymogami, nie będzie można zwolnić wariantów za pomocą sugestii wariantów. Nie będzie również możliwe ręczne tworzenie wariantów.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to celowe. Relacje produktu głównego i wymiarów, które może wykonać produkt główny, są utrzymywane na poziomie udostępnionym. Dlatego nie można utworzyć wymiarów dostępnych dla udostępnionego produktu głównego w określonej osobie prawnej, w której te wymiary są zwolnione, a następnie replikować proces w każdej osobie prawnej, w której są wymagane wymiary. W takim przypadku należy zmienić proces wydania w celu dostosowania go do planowanego procesu.

Poniżej przedstawiono proces zwalniania produktów.

1. Utwórz współużytkowany produkt główny i wymiary, które można zwolnić do osób prawnych.
1. Umożliwia zwolnienie produktów do osób prawnych przez użycie sugestii wariantów lub ręczne dodanie kombinacji, które powinny zostać zwolnione.

Można również bezpośrednio utworzyć zwolniony produkt.

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a>Po zwolnieniu wariantu w innej osobie prawnej otrzymuję następujący komunikat o błędzie: „Wariant produktu o określonych wymiarach został już utworzony”.

### <a name="issue-description"></a>Opis problemu

Jeśli wariant produktu został już wydany w firmie A i podjęto próbę zwolnienia go w firmie B za pomocą przycisku **Nowy** na stronie **Zwolnione warianty produktu**, zostanie wyświetlony następujący komunikat o błędzie:

> Wariant produktu o podanych wymiarach został już utworzony.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Przycisk **Nowy** na stronie **Zwolnione warianty produktu** powoduje utworzenie wariantu i zwolnienie go w kontekście firmy. Jeśli wariant został już utworzony, nie można go zwolnić w innej firmie przy użyciu przycisku **Nowy**.

Aby rozwiązać ten problem, otwórz stronę **Produktu głównego** i wybierz pozycję **Zwolnij produkt**, aby zwolnić istniejący wariant w wybranej firmie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]