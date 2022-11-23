---
title: Eksportowanie danych oddziałów do plików
description: W tym artykule wyjaśniono, jak przygotować się do wyeksportowania danych z Microsoft Dynamics 365 Finance, a następnie zaimportowania ich do skonsolidowanej firmy.
author: jinniew
ms.date: 11/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 30d69f9a2813621df410a29568644f264392fb49
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779969"
---
# <a name="export-subsidiary-data-to-files"></a>Eksportowanie danych oddziałów do plików

[!include [banner](../includes/banner.md)]

Strona **Eksportu** umożliwia (**Administrowanie systemem \> Obszary robocze \> Import/Eksport**) przygotowanie do eksportowania danych oddziałów do plików, które następnie można zaimportować do firmy skonsolidowanej. Więcej informacji o procesach importu i eksportu, zapoznaj się z [Omówieniem importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

1. Utwórz firmę dla procesu konsolidacji. Aby uzyskać informacje na temat tworzenia firm, zapoznaj się z tematem [Tworzenie firmy](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Aby uzyskać więcej informacji, zobacz temat [Przygotowanie firmy do użycia w procesie konsolidacji](prepare-company-for-consolidation.md) i [Konfigurowanie firmy zależnej do konsolidacji](set-up-subsidiary-company-for-consolidation.md). 

2. Przejdź do **Konsolidacje \> Eksportuj salda firmy**. Na stronie **Eksportuj salda firmy** na karcie **Kryteria** określ szczegóły konsolidacji, ustawiając następujące pola.

    | Pole                             | opis |
    |-----------------------------------|-------|
    | **Konto główne**                      | Określ konta do konsolidacji. Aby uwzględnić wszystkie konta, należy pozostawić to pole puste. |
    | **Użyj konta konsolidacji**         | Jeśli określono konta konsolidacji, ustaw tę opcję na wartość **Tak**. |
    | **Wybierz konto konsolidacji z** | Wybierz **Konto główne** lub **Grupę kont konsolidacji**. |
    | **Grupa kont konsolidacji**       | Wybierz grupę kont konsolidacyjnych dla wybranego konta konsolidacyjnego. |
    | **Okres konsolidacji**              | Określ daty „od” i „do” konsolidacji. |
    | **Uwzględnij kwoty rzeczywiste**            | Ustaw dla tej opcji wartość **Tak**, aby uwzględnić dokładne wartości rzeczywiste. |
    | **Uwzględnij kwoty budżetu**            | Ustaw dla tej opcji wartość **Tak**, aby uwzględnić kwoty budżetu w konsolidacjach. |
    | **Modele budżetu**                     | Określ model budżetu, który ma być uwzględniany. |

3. Na karcie **Wymiary finansowe** podaj szczegóły konsolidacji:

    - Podaj informacje o wymiarze finansowym, które są przenoszone z transakcji kont oddziałów do transakcji firmy konsolidowanej.
    - Wybierz wymiary finansowe z listy.
    - Określ poprawną specyfikację dla każdego konsolidowanego wymiaru finansowego. Dostępne opcje to **Wymiar**, **Wymiar grupy**, **Firma** i **Konto**.

        > [!NOTE]
        > Opcja **Grupuj wymiary** umożliwia definiowanie wartości wymiaru używanej przez grupę firm, które są konsolidowane.

    - Określ kolejność segmentów do konsolidacji.

4. Na karcie **Firmy** wykonaj następujące kroki, aby określić eksportowanie firmy:

    1. Wybierz pozycję **Nowy**.
    2. W polu **Firma źródłowa** wprowadź nazwę firmy.

        Jeśli identyczne kryteria dotyczą kilku oddziałów z tej samej bazy danych, za pomocą jednej operacji można przenieść dane oddziałów znajdujące się w tej samej bazie danych do osobnych plików eksportu:

        1. Utwórz wiersz dla każdej zależnej firmy, dla której konta mają zostać wyeksportowane do plików. Pliki te zostaną później zaimportowane do skonsolidowanej osoby prawnej.
        2. Dla każdego oddziału wprowadź nazwę oddziału i nazwę pliku eksportu, który zostanie utworzony podczas zadania eksportu.

    3. W polu **Typ konta różnic konwersji** wybierz pozycję **Wynikowe** lub **Bilans**.
    4. Wprowadź nazwę pliku eksportu, który zostanie utworzony.

5. Wybierz przycisk **OK**, aby uruchomić eksport.

Po zakończeniu eksportu zostanie wyświetlony komunikat zawierający liczbę rekordów zapisanych w każdym pliku. Następnie można importować pliki w skonsolidowanej firmie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
