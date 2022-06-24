---
title: Przygotowanie firmy w procesie konsolidacji
description: Podczas konsolidacji transakcje z kilku zestawów kont podmiotów prawnych są gromadzone w jednym zestawie kont podmiotów prawnych. W tym artykule wyjaśniono, jak przygotować firmę do konsolidacji.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 2a3d4645c79ec30df2bbb7a32a82a59fdb7016e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894034"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a>Przygotowanie firmy w procesie konsolidacji

[!include [banner](../includes/banner.md)]

Podczas konsolidacji transakcje z kilku zestawów kont podmiotów prawnych są gromadzone w jednym zestawie kont podmiotów prawnych. W tym artykule wyjaśniono, jak przygotować firmę do konsolidacji.

> [!NOTE]
> Zalecamy użycie narzędzia Management Reporter dla Microsoft Microsoft Dynamics 365 Finance w celu połączenia wyników finansowych wielu firm w skonsolidowanym formacie. Program Management Reporter umożliwia tworzenie skonsolidowanych raportów finansowych dla różnych firm, używanie programu Excel do importowania danych konsolidacji z innych źródeł oraz przetłumaczenie kwot na dowolną liczbę walut raportowania bez konieczności uruchamiania procesu konsolidacji w Dynamics 365 Finance.

Można wydrukować raporty, takie jak sprawozdania finansowe z firmy skonsolidowanej. Jednak nie można użyć firmy skonsolidowanej dla transakcji dziennych.

Można konsolidować dane z firm, które używają innych baz danych niż firma skonsolidowana. Ten proces konsolidacji jest nazywany *konsolidacją importu*. Firmy mogą także użyć tej samej bazy danych jako skonsolidowane firmy. Ten proces konsolidacji jest nazywany *konsolidacją online*.

Firma skonsolidowana gromadzi wyniki i salda swoich oddziałów. W celu przygotowania firmy skonsolidowanej do konsolidacji, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Księga główna \> Konfiguracja \> Organizacja \> Firmy**.
2. Kliknij opcje **Nowy**, aby utworzyć nowy podmiot prawny, który będzie konsolidowaną firmą.
3. Zaznacz pole wyboru **Użyj w procesie konsolidacji finansowej**, a następnie wprowadź informacje o konsolidowanej firmie. Pamiętaj, aby wprowadzić te informacje dokładnie tak, jak chcesz, aby pojawiały się w sprawozdaniach finansowych podmiotu prawnego objętego konsolidacją.
4. Zamknij stronę.
5. Wybierz firmę skonsolidowaną w polu w prawym górnym rogu strony, a następnie wybierz **OK**.
6. Wybierz kolejno opcje **Księga główna \> Ustawienia \> Księga**.
7. Umożliwia wybranie planu kont, kalendarza obrachunkowego, waluty rozliczeniowej, opcjonalnej waluty raportowania i domyślnego typu kursu wymiany dla konsolidowanej firmy. 
8. Wybierz kolejno opcje **Księga główna \> Ustawienia \> Waluta \> Kursy wymiany waluty**.
9. Skonfiguruj kursy wymiany w odpowiednich okresach dla walut oddziałów firm.
10. Zamknij stronę.
11. Jeśli firma skonsolidowana ma przedstawicielstwa, które używają walut obcych, wykonaj następujące kroki:

    1. Wybierz kolejno opcje **Księga główna \> Ustawienia \> Księgowanie \> Konta dla transakcji automatycznych**.
    2. W polu **Typ księgowania** wybierz odpowiednie konto:

        - Jeśli podmiot prawny ma zagraniczne spółki zależne, które są współzależne finansowo lub operacyjnie z podmiotem dominującym, wybierz odpowiednie konto dla **Rachunku zysków i strat dla różnic konsolidacyjnych** typu księgowania.
        - Jeżeli następuje konsolidowanie oddziału, który jest finansowo i funkcjonalnie niezależny od firmy nadrzędnej lub podmiotu prawnego, z wynikami kilku oddziałów, które są finansowo i funkcjonalnie niezależne od firmy nadrzędnej i jeśli korzysta się z metod przeliczania walut do konsolidowania danych, należy wybrać odpowiednie konto dla **Konto bilansowe na potrzeby różnic konsolidacji** typu księgowania.

    3. W polu **Główne konto** wybierz konta główne, które będą używane dla korekty przeszacowania w walucie obcej.
    4. Zamknij stronę.

    Jeśli tworzysz firmę skonsolidowaną na początku okresu, możesz dostosować kwoty walut obcych według zmian kursu wymiany w trakcie okresu konsolidacji.

Firma skonsolidowanej jest teraz skonfigurowana jako zadanie okresowe **Konsolidacja**. Można wykonać konsolidację importu lub konsolidację online.

- Aby przeprowadzić konsolidację importu, przejdź do **Księga główna \> Okresowe \> Konsolidacja \> Konsolidacja \[Importuj z\]**.
- Aby przeprowadzić konsolidację online, przejdź do **Księga główna \> Okresowe \> Konsolidacja \> Konsolidacja \[Online\]**.

> [!NOTE]
> Zanim będzie można przeprowadzić konsolidację, należy przygotować do niej oddziały firmy. Aby zapoznać się z dodatkowymi informacjami, zobacz [Konfigurowanie firmy zależnej do konsolidacji](set-up-subsidiary-company-for-consolidation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
