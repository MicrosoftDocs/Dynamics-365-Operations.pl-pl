---
title: Zezwalaj na edycje danych wewnętrznych w załącznikach księgi głównej
description: Ten artykuł zawiera informacje dotyczące edytowania danych wewnętrznych w załącznikach księgi głównej.
author: kweekley
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 6e346c6ff881d3a33743196b45247493fd19ed1d
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573259"
---
# <a name="allow-edits-to-internal-data-on-general-ledger-vouchers"></a>Zezwalaj na edycje danych wewnętrznych w załącznikach księgi głównej

[!include[banner](../includes/banner.md)]


Podczas księgowania zapisów księgowych w księdze głównej pole **Opis** jest często używane do przechowywania notatek wewnętrznych lub dokumentacji. Jeśli informacje są niepoprawne, może to spowodować nieporozumienie i utrudnić zamknięcie na koniec okresu. Ta funkcja umożliwia kierownikowi księgowości lub kierownikowi księgowości naprawienie błędów przez edycję pola **Opis** dla zaksięgowanych załączników w księdze głównej.

Zmiany zaksięgowanych załączników w księdze głównej są ograniczone do danych o charakterze wewnętrznym. Ta funkcja nigdy nie zezwala na edycję danych, takich jak kwoty, daty księgowania, konta księgowe i waluta transakcji. Zmiany tych danych wpłyną na zewnętrzne raportowanie sprawozdań finansowych i muszą być wykonywane tylko za pośrednictwem nowych załączników księgi głównej.

> [!NOTE]
> W przypadku oprogramowania Dynamics 365 Finance w wersji 10.0.29 ta funkcja jest ograniczona do edycji w **polu Opis**.

## <a name="edit-internal-data-on-general-ledger-vouchers"></a>Edycja danych wewnętrznych w załącznikach księgi głównej

Aby można było edytować dane wewnętrzne w załącznikach księgi głównej, należy włączyć funkcję **Zezwalaj na edycje danych wewnętrznych w załącznikach księgi głównej** w obszarze roboczym **Zarządzanie funkcjami**.
Gdy ta funkcja jest włączona, użytkownik, który będzie edytować zaksięgowane załączniki, musi być przypisany do roli Kierownik ds. księgowości lub Kierownik ds. księgowości. Można również dodawać uprawnienia do innych ról, do dostosowywania ról zabezpieczeń.

Proces edycji jest dozwolony tylko ze strony Transakcje na załączniku.

1. Wybierz kolejno opcje **Księga główna** > **Zapytania i raporty** > **Transakcje na załączniku**.
2. W oknie dialogowym **SysQuery** wprowadź kryteria wyszukiwania, aby wybrać załączniki.
3. Zaznacz wiersze załączników, które chcesz edytować, a następnie **Edytuj załącznik** > **Edytuj dane załącznika wewnętrznego**.

    [![Strona transakcji załącznika.](./media/voucher-transactions-page.png)](./media/voucher-transactions-page.png)
    
Na stronie **Edycja danych załączników wewnętrznych** dla każdego wybranego wiersza są wyświetlane następujące dane:
  
  - Konto finansowe
  - Nazwa konta
  - Załącznik
  - Bieżący opis
  - Nowy opis

    [![Załącznik arkusza.](./media/edit-internal-voucher-data.png)](./media/edit-internal-voucher-data.png)
    
> [!NOTE]
> Można edytować tylko pole **Nowy opis**. Domyślnie ta wartość odpowiada wartości w polu **Bieżący opis**, dzięki czemu można szybko poprawić drobne błędy w opisie.

4. Zmodyfikuj **pole Nowy opis** w każdym wierszu lub usuń opis z każdego wiersza.

   Ewentualnie, jeśli wiele wierszy musi zostać zaktualizowanych o tę samą wartość, należy wykonać następujące czynności:

      1. Wybierz wiersze do edycji, a następnie wybierz opcję **Aktualizacja zbiorcza wybranych rekordów**.
      2. W polu **Pole do edycji** wybierz pole do edycji. Obecnie pole Wyszukiwania zawiera tylko **pole Nowy opis**.
      3. W polu **Nowa wartość** wpisz opis nowej wartości.
      4. Wybierz **Aktualizuj**. Wszystkie wybrane rekordy zostaną zaktualizowane nową wartością.

      [![Okno Masowe aktualizowanie zaznaczonych rekordów.](./media/bulk-update-selected-records.png)](./media/bulk-update-selected-records.png)
    
5. W polu **Przyczyna edycji** wprowadź notatkę, aby podać przyczynę tej edycji. Ta uwaga jest wyświetlana na stronie **Dziennik inspekcji edytowania załączników**.

   Istnieje możliwość wielu edycji tego samego załącznika, a każda edycja jest śledzona.

## <a name="audit-trail-of-voucher-edits"></a>Dziennik inspekcji edycji załączników

Dziennik inspekcji jest zachowywany specjalnie w celu śledzenia zmian wprowadzonych za pomocą tej funkcji. Dziennik inspekcji edycji załączników można uzyskać na dwa sposoby:

  - Wybierz kolejno opcje **Księga główna** > **Zapytania i raporty** > **Transakcje na załączniku**. Na stronie **Informacje o załącznikach** wybierz pozycję **Edytuj załącznik** > **Dziennik inspekcji edycji załączników**. Dziennik inspekcji jest wyświetlany tylko dla wybranego rekordu załącznika. 
   
    Otwierając zapytanie w ten sposób, można koncentrować się na wszystkich edycjach wykonanych dla jednego rekordu załącznika.
  
  - Przejdź do **Księga główna** > **Zadania okresowe** > **Dziennik inspekcji edycji załączników**. W oknie dialogowym wprowadź kryteria określania załączników, dla których chcesz wyświetlić dziennik inspekcji edycji. Aby wyświetlić dziennik inspekcji dla wszystkich załączników, pozostaw kryteria puste i wybierz przycisk **OK**. 
    
    Otwierając zapytanie w ten sposób, można odfiltrować zmiany dokonane w określonym dniu lub przez określonego użytkownika.

Na **stronie Dziennik inspekcji edycji** są podane następujące informacje:

- **Data i godzina utworzenia** — data i godzina edycji.
- **Przyczyna edycji** — przyczyna wprowadzona przez użytkownika do edycji.
- **Utworzone przez** – Użytkownik, który dokonał zmiany.

Aby wyświetlić szczegóły każdego dziennika inspekcji, przejdź do szczegółów wartości **Data i godzina utworzenia**. Strona **Wyświetlanie edytowanych właściwości załącznika zawiera** te same informacje co oryginalna strona edycji, w tym poprzedni opis i zaktualizowany opis.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
