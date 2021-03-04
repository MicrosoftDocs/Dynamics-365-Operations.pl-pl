---
title: Projektowanie konfiguracji raportowania elektronicznego w celu generowania raportów w formacie programu Word
description: W poniższych krokach wyjaśniono, jak użytkownik posiadający rolę Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować formaty raportowania elektronicznego, aby raporty były generowane jako pliki programu Microsoft Word.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d4959b511022e1aa98544d23da6afcda1f6adf2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681932"
---
# <a name="design-er-configurations-to-generate-reports-in-word-format"></a>Projektowanie konfiguracji raportowania elektronicznego w celu generowania raportów w formacie programu Word

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik posiadający rolę Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować formaty raportowania elektronicznego (ER), aby raporty były generowane jako pliki programu Microsoft Word. Kroki można wykonać na danych firmy GBSI.

W celu wykonania tych kroków należy najpierw wykonać kroki opisane w przewodniku po zadaniu „Tworzenie konfiguracji ER do generowania raportów w formacie OPENXML”. Należy również wcześniej pobrać i zapisać następujące szablony lokalnie dla przykładowego raportu:

- [Szablon raportu o płatnościach](https://go.microsoft.com/fwlink/?linkid=862266)
- [Ograniczony szablon raportu o płatnościach](https://go.microsoft.com/fwlink/?linkid=862266)


Procedura dotyczy funkcji dodanej w programie Microsoft Dynamics 365 for Operations w wersji 1611.


## <a name="select-the-existing-er-report-configuration"></a>Zaznaczenie istniejącej konfiguracji raportu ER
1. W **okienku nawigacji przejdź do Moduły > Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne**. Upewnij się, że dostawca konfiguracji „Litware, Inc.” jest oznaczony jako aktywny.  
2. Kliknij opcję **Konfiguracje raportowania**. Ponownie wykorzystamy istniejącą konfigurację ER, który została pierwotnie zaprojektowana do generowania danych wyjściowych raportu w formacie OPENXML.  
3. W drzewie rozwiń „model płatności”.
4. W drzewie zaznacz węzeł „Model płatności\Przykładowy raport arkusza”.
5. Kliknij przycisk Konstruktor.

## <a name="replace-the-excel-template-with-the-word-template"></a>Zastąpienie szablonu programu Excel szablonem programu Word

Obecnie dokument programu Excel jest używany jako szablon do generowania danych wyjściowych w formacie OPENXML. Zaimportujemy szablon raportu w formacie programu Word.

1. Kliknij **Załączniki**. Zastąp istniejący szablon programu Excel szablonem programu Word, który został pobrany wcześniej (SampleVendPaymDocReport.docx). Zwróć uwagę, że ten szablon zawiera tylko układ dokumentu, który chcemy wygenerować jako dane wyjściowe raportowania elektronicznego.  
2. Kliknij przycisk **Usuń**.
3. Kliknij przycisk **Tak**.
4. Kliknij przycisk **Nowy**.
5. Kliknij opcję **Plik**.
6. Kliknij **Przeglądaj**. Odszukaj i zaznacz szablon SampleVendPaymDocReport.docx, który został wcześniej pobrany. Kliknij przycisk **OK**. Zaznacz szablon pobrany w poprzednim kroku.  
7. W polu **Szablon** wprowadź lub wybierz wartość.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Rozszerzenie szablonu programu Word przez dodanie niestandardowej części XML
1. Kliknij przycisk **Zapisz**. Oprócz zapisania zmian w konfiguracji akcja Zapisz aktualizuje także dołączony szablon programu Word. Struktura zaprojektowanego formatu jest przenoszona do dołączonego dokumentu programu Word jako nowy niestandardowa część w postaci kodu źródłowego XML o nazwie „Raport”. Należy zauważyć, że dołączony szablon programu Word zawiera nie tylko układ dokumentu, który chcemy wygenerować jako dane wyjściowe modułu ER, ale również strukturę danych, które moduł raportowania elektronicznego umieści w tym szablonie podczas wykonywania.  
2. Kliknij **Załączniki**.
    + Teraz należy powiązać elementy niestandardowego fragmentu XML „Raport” z częściami będącymi dokumentem programu Word.  
    + Jeśli masz wystarczającą wiedzę o dokumentach programu Word, które można projektować jako formularze zawierające formanty treści powiązane z elementami niestandardowych części XML, odtwórz kroki następnego podzadania, aby utworzyć taki dokument. Więcej informacji zawiera sekcja [Tworzenie formularzy, które użytkownicy wypełniają lub drukują w aplikacji Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US). W przeciwnym razie pomiń wszystkie kroki następnego podzadania.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Pobranie dokumentu programu Word z niestandardową częścią XML w celu utworzenia powiązań danych

Otwórz ten dokument w programie Word i wykonaj następujące czynności:  
1. Otwórz kartę Deweloper programu Word (jeśli nie jest jeszcze włączona, dostosuj odpowiednio wstążkę).
2. Kliknij okienko Mapowanie XML.
3. Na liście odnośników zaznacz niestandardowa część XML „Raport”.
4. Zamapuj elementy wybranej niestandardowej części XML i formanty zawartości dokumentu programu Word.  5. Zapisz zaktualizowany dokument programu Word na dysku lokalnym.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Przekazanie szablonu dokumentu programu Word z niestandardową częścią XML do formantów zawartości
1. Kliknij przycisk **Usuń**.
2. Kliknij przycisk **Tak**. Dodaj nowy szablon. Jeśli wykonano kroki opisane w poprzednim podzadaniu, zaznacz dokument programu Word, który został przygotowany i zapisany lokalnie. W przeciwnym razie zaznacz pobrany wcześniej szablon programu MS Word SampleVendPaymDocReportBounded.docx.  
3. Kliknij przycisk **Nowy**.
4. Kliknij opcję **Plik**.
5. Kliknij **Przeglądaj**. Odszukaj i zaznacz szablon SampleVendPaymDocReportBounded.docx, który został wcześniej pobrany. Kliknij przycisk **OK**.
6. W polu **Szablon** zaznacz dokument pobrany w poprzednim kroku.
7. Kliknij przycisk **Zapisz**.
8. Zamknij stronę.

## <a name="execute-the-format-to-create-word-output"></a>Uruchomienie formatu w celu utworzenia danych wyjściowych programu Word
1. W **okienku akcji** kliknij pozycję **Konfiguracje**.
2. Kliknij opcję **Parametry użytkownika**.
3. W polu **Ustawienia uruchamiania** wybierz opcję Tak.
4. Kliknij przycisk **OK**.
5. Kliknij przycisk **Edytuj**.
6. W polu **Uruchom wersję roboczą** wybierz opcję Tak.
7. Kliknij przycisk **Zapisz**.
8. Zamknij stronę.
9. Zamknij stronę.
10. W **okienku nawigacji** przejdź do **Moduły > Rozrachunki z dostawcami > Płatności > Arkusz płatności**.
11. Kliknij przycisk **Wiersze**.
12. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
13. Kliknij opcję **Stan płatności**.
14. Kliknij opcję **Brak**.
15. Kliknij opcję **Generuj płatności**.
16. Kliknij przycisk **OK**.
17. Kliknij przycisk **OK**. Zbadaj wygenerowane dane wyjściowe. Zwróć uwagę, że utworzone dane wyjściowe są przedstawione w formacie programu Word i zawierają szczegóły przetworzonych płatności.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]