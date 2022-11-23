---
title: Importowanie danych przedstawicielstw z plików
description: W tym artykule wyjaśniono, jak przygotować dane z systemów zewnętrznych, aby można je było zaimportować do Microsoft Dynamics 365 Finance.
author: jinniew
ms.date: 10/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 494f6396d5e6fab6fef9404ad473566b02b1b9ab
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780104"
---
# <a name="import-subsidiary-data-from-files"></a>Importowanie danych przedstawicielstw z plików

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak przygotować dane z systemów zewnętrznych, aby można je było zaimportować do Microsoft Dynamics 365 Finance. Strona **Konsoliduj ze importem** (**Konsolidacje \> Konsoliduj z importem**) umożliwia przygotowanie przeniesienia danych oddziałów z systemów zewnętrznych.

1. Utwórz osoba prawna zależną na potrzeby konsolidacji. Aby uzyskać informacje na temat tworzenia firm, zapoznaj się z tematem [Tworzenie firmy](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Aby uzyskać więcej informacji, zobacz temat [Przygotowanie firmy do użycia w procesie konsolidacji](prepare-company-for-consolidation.md) i [Konfigurowanie firmy zależnej do konsolidacji](set-up-subsidiary-company-for-consolidation.md).

2. Przygotuj plik, który będzie zawierał importowane dane. Więcej informacji o procesie importu, zapoznaj się z [Omówieniem importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
3. Wyeksportuj dane do pliku, wykonując czynności opisane w procedurze „Proces importu / eksportu danych” w [Omówienie zadań importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). Możesz użyć tej procedury do konsolidacji danych z innego wystąpienia Dynamics 365 Finance lub z Dynamics 365 Business Central. Jeśli importujesz dane z systemów zewnętrznych, dane muszą być w formacie opisanym w temacie [Eksportowanie danych oddziałów do plików](export-subsidiary-data-to-file.md).
4. Wybierz kolejno opcje **Konsolidacje \> Konsoliduj z importem**. Na stronie **Konsoliduj z importem** na karcie **Kryteria** określ szczegóły raportu i/lub importu, ustawiając następujące pola.

| Pole                                 | Wartość raportu | Wartość do raportu |
|---------------------------------------|----------------------|----------------------|
| **opis**                      | Nie dotyczy | Wprowadź opis, aby zidentyfikować import. |
| **Konto główne**    | Zdefiniuj zakres kont, które powinny być zawierane w raporcie. Jeśli nie zdefiniujesz zakresu, zostaną uwzględnione wszystkie konta. | Zdefiniuj zakres kont, które powinien obejmować import. Jeśli nie zdefiniujesz zakresu, zostaną uwzględnione wszystkie konta. |
    | **Okres konsolidacji**                  | Zdefiniuj zakres dat do konsolidacji. | Zdefiniuj zakres dat do konsolidacji. |
    | **Uwzględnij kwoty rzeczywiste**                | Ustaw dla tej opcji wartość **Tak**, aby uwzględnić wartości rzeczywiste. | Ustaw dla tej opcji wartość **Tak**, aby uwzględnić wartości rzeczywiste. |
| **Uwzględnij kwoty budżetu** | Ustaw dla tej opcji wartość **Tak**, aby uwzględnić kwoty budżetu w konsolidacjach. | Ustaw dla tej opcji wartość **Tak**, aby uwzględnić kwoty budżetu w konsolidacjach. |
| **Przebudowa sald podczas konsolidacji** | Ustaw tę opcję na wartość **Tak**, jeśli proces odbudowy powinien całkowicie wyczyścić saldo i nowe rekordy oraz odtworzyć równowagę od początku czasu. | Ustaw tę opcję na wartość **Tak**, jeśli proces odbudowy powinien całkowicie wyczyścić saldo i nowe rekordy oraz odtworzyć równowagę od początku czasu. |
| **Modele budżetu**                         | Nie dotyczy | Jeśli wybrano importowanie kwot budżetu, wprowadź modele budżetu do konsolidacji. |
    | **Typ kursu budżetowego**                      | Nie dotyczy | Wpisz typ kursu wymiany budżetu. |

6. Jeśli masz różne waluty rozliczeniowe, użyj pól na karcie **Przeliczenie walut**, aby skonfigurować tłumaczenie, które jest wykonywane podczas konsolidacji.

    | Pole                      | opis |
    |----------------------------|-------------|
 | **Firma źródłowa**        | Wybierz osobę prawną, z której importujesz. |
 | **Źródłowa waluta rozliczeniowa** | Ta waluta domyślna jest walutą skojarzoną z firma źródłową wybraną w polu **Firma źródłowa**. |
 | Konta **od** i **do**       | Zdefiniuj zakres kont do zaimportowania ze źródłowej firmy. |
    | **Typ kursu wymiany**         | Wybierz rodzaj kursu wymiany. Typy kursów wymiany są przypisywane podczas tworzenia konta głównego. Aby uzyskać więcej informacji, zobacz [Tworzenie konta głównego](tasks/create-main-account.md). |
| **Zastosuj kurs wymiany od**   | Wprowadź datę, aby zastosować kurs wymiany, który obowiązywał w tym dniu. Alternatywnie wprowadź wartość, która ma być używana jako kurs wymiany. |
| **Kurs wymiany**  | Wartość domyślna zależy od typu kursu wymiany wybranego w polu **Typ kursu wymiany**. Po wprowadzeniu kursu wymiany zdefiniowanego przez użytkownika można zdefiniować kurs. |

7. Ustaw opcję **Uruchom w tle** na wartość **Tak**, aby proces importowania był uruchamiany w tle.
8. Ustaw opcję **Przetwarzanie wsadowe** na **Tak**, aby konsolidacja uruchamiała się jako zadanie wsadowe w określonym czasie. Aby natychmiast uruchomić konsolidację, wybierz przycisk **OK**. 

Transakcje i salda, które zostały wskazane do konsolidacji w oddziałach, zostaną dodane do odpowiednich kont firmy skonsolidowanej.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
