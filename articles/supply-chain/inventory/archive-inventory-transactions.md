---
title: Archiwizuj transakcje magazynowe
description: W tym artykule opisano sposób archiwizowania danych transakcji magazynowych w celu zwiększenia wydajności systemu.
author: yufeihuang
ms.date: 05/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c63cdee862e2e22649a3eb58ae37597741770e14
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874109"
---
# <a name="archive-inventory-transactions"></a>Archiwizuj transakcje magazynowe

[!include [banner](../../includes/banner.md)]

Z czasem tabela transakcji magazynowych (`InventTrans`) będzie nadal wzrastać i zużywać więcej miejsca w bazie danych. Z tego względu kwerendy wykonane dla tej tabeli będą stopniowo coraz wolniejsze. W tym artykule opisano, jak można używać funkcji *Archiwizuj transakcje magazynowe* do archiwizowania danych dotyczących transakcji magazynowych w celu zwiększenia wydajności systemu.

> [!NOTE]
> W wybranym zamkniętym okresie finansowym można zarchiwizować tylko finansowo zaktualizowane transakcje magazynowe. Aby można było zarchiwizować, finansowo zaktualizowane wychodzące transakcje magazynowe muszą mieć stan wydania *Sprzedane*, a przychodzące transakcje magazynowe muszą mieć stan przyjęcia *Zakupione*.

Podczas archiwizowania transakcji magazynowych wszystkie powiązane transakcje są przenoszone do tabeli `InventTransArchive`. Transakcje rozchodów magazynowych i transakcje przyjęcia materiałów są archiwizowane oddzielnie na podstawie kombinacji identyfikatora towaru (`itemId`) i identyfikatora wymiaru magazynowego (`inventDimId`) i są umieszczane w podsumowanych transakcjach rozchodów i zsumowanych przyjęć.

Jeśli kombinacja `itemId` i `inventDimId` zawiera tylko jedną transakcję przyjęcia lub wydania, transakcja nie zostanie zarchiwizowana.

## <a name="turn-on-the-feature-in-your-system"></a>Włączanie funkcji w systemie

Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym artykule, przejdź do [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Archiwum transakcji magazynowych*. Należy pamiętać, że tej funkcji nie można wyłączyć po jej włączeniu.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Co należy wziąć pod uwagę przed zarchiwizować transakcje magazynowe

Przed zarchiwizowania transakcji magazynowych należy uwzględnić następujące scenariusze biznesowe, ponieważ operacja będzie dotyczyć ich:

- Podczas inspekcji transakcji magazynowych z powiązanych dokumentów, takich jak wiersze zamówień zakupu, są one pokazywane jako zarchiwizowane. Aby przejrzeć zarchiwizowane transakcje, musisz przejść do **Zarządzanie zapasami \> Zadania okresowe \> Oczyszczanie \> Archiwum transakcji magazynowych**.
- Nie można anulować zamknięcia magazynu dla zarchiwizowanego okresu. Aby było można anulować zamknięcie magazynu, należy wycofać archiwum transakcji magazynowych dla odpowiedniego okresu.
- Nie można wykonać konwersji na koszt standardowy dla zarchiwizowanego okresu. Przed wykonaniem standardowej konwersji kosztu należy wycofać archiwum transakcji magazynowych dla odpowiedniego okresu.
- Archiwizacja transakcji magazynowych ma wpływ na raporty zapasów, które pochodzą z transakcji magazynowych. Raporty te zawierają raporty wiekowania zapasów i raporty wartości zapasów.
- Może to mieć wpływ na prognozy zapasów, jeśli są uruchamiane w czasie horyzontu zarchiwizowanego okresu.

## <a name="prerequisites"></a>Wymagania wstępne

Transakcje magazynowe można zarchiwizować tylko w okresach, w których są spełnione następujące warunki:

- Okres księgi musi być zamknięty.
- Zamykanie magazynu musi być uruchomione do daty archiwum lub późniejsza.
- Okres musi być co najmniej rok przed datą od okresu archiwum.
- Nie mogą być żadne istniejące ponowne przeliczenia zapasów.

## <a name="archive-inventory-transactions"></a>Archiwizuj transakcje magazynowe

Aby zarchiwizować transakcje magazynowe, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie zapasami** \> **Zadania okresowe** \> **Oczyszczanie** \> **Archiwum transakcji magazynowych**.

    Zostanie wyświetlona strona **Archiwum transakcji magazynowych** z listą zarchiwizowanego rekordu procesu.

    ![Strona Archiwum transakcji magazynowych.](media/archive-inventory-empty.png "Strona Archiwum transakcji magazynowych")

1. W okienku akcji wybierz opcję **Archiwum transakcji magazynowych**, aby utworzyć archiwum transakcji magazynowych.
1. W oknie dialogowym **Archiwum transakcji magazynowych** na skróconej karcie **Parametry** ustaw następujące pola:

    - **Od dnia w zamkniętym okresie księgi** — umożliwia wybór najwcześniejszej daty transakcji do archiwizacji.
    - **Do dnia w zamkniętym okresie księgi** — umożliwia wybór najpóźniejszej daty transakcji do archiwizacji.

    ![Okno dialogowe Archiwum transakcji magazynowych.](media/archive-inventory-dates.png "Okno dialogowe Archiwum transakcji magazynowych")

    > [!NOTE]
    > Do wyboru będą dostępne tylko okresy spełniające [wymagania wstępne](#prerequisites).

1. Na skróconej karcie **Uruchom w tle** skonfiguruj szczegóły przetwarzania wsadowego. W przypadku zadań wsadowych w Microsoft Dynamics 365 Supply Chain Management wykonaj typowe czynności.
1. Kliknij przycisk **OK**.
1. Zostanie wyświetlony komunikat z monitem o potwierdzenie, że chcesz kontynuować. Przeczytaj uważnie wiadomość, a następnie wybierz przycisk **Tak**, jeśli chcesz kontynuować.

    Zostanie wyświetlony komunikat informujący, że zadanie archiwum transakcji magazynowych zostało dodane do kolejki przetwarzania wsadowego. Zadanie rozpocznie teraz archiwizację transakcji magazynowych z wybranego okresu.

## <a name="view-archived-inventory-transactions"></a>Wyświetl zarchiwizowane transakcje magazynowe

Strona **Archiwum transakcji magazynowych** pokazuje pełną historię archiwizacji. Każdy wiersz w siatce zawiera informacje, takie jak data utworzenia archiwum, użytkownik, który je utworzył, oraz jego stan.

![Archiwizacja historii na stronie archiwum transakcji magazynowych.](media/archive-inventory-full.png "Archiwizacja historii na stronie archiwum transakcji magazynowych")

Z listy rozwijanej w górnej części strony wybierz jedną z następujących wartości, aby przefiltrować archiwa pokazywane w siatce:

- **Aktywne** — pokazywane są tylko aktywne archiwa, a nie wycofane archiwa.
- **Wszystkie** — pokazywane są wszystkie archiwa, aktywne i wycofane.

Dla każdego archiwum w siatce są dostarczane następujące informacje:

- **Aktywne** — znacznik wyboru wskazuje, że archiwum jest aktywne.
- **Od daty** — data najstarszej transakcji, która może zostać uwzględniona w archiwum.
- **Do daty** — data najpóźniejszej transakcji, która może zostać uwzględniona w archiwum.
- **Zaplanowane przez** — konto użytkownika, który utworzył archiwum.
- **Wykonane** – Data i godzina utworzenia archiwum.
- **Wycofanie** — znacznik wyboru wskazuje, że archiwum zostało wycofane.
- **Zatrzymaj bieżącą aktualizację** — znacznik wyboru wskazuje, że archiwum jest w toku, ale zostało wstrzymane.
- **Stan** — stan przetwarzania archiwum. Możliwe wartości to *Oczekujące*, *W toku* i *Zakończone*.

Pasek narzędzi nad siatką zawiera następujące przyciski, których można używać do pracy z wybranym archiwum:

- **Zarchiwizowane transakcje** – Umożliwia wyświetlenie wszystkich szczegółów wybranego archiwum. Na stronie **Zarchiwizowane transakcje** wyświetlane są wszystkie transakcje z archiwum.

    ![Strona zarchiwizowanej transakcji.](media/archive-inventory-transactions.png "Strona zarchiwizowanej transakcji")

    Aby wyświetlić więcej informacji o określonej transakcji na stronie **Zarchiwizowane transakcje**, zaznacz ją w siatce, a następnie w okienku akcji wybierz opcję **Szczegóły zarchiwizowanej transakcji**. Na stronie **Szczegółów zarchiwizowanych transakcji** są wyświetlane informacje, takie jak księgowanie w księdze, powiązane odwołania do księgi podrzędnej i wymiary finansowe.

- **Wstrzymywanie archiwizacji** — wstrzymanie wybranego archiwum, które jest obecnie przetwarzane. Wstrzymanie następuje dopiero po wygenerowaniu zadania archiwizacji. Dlatego może wystąpić krótkie opóźnienie, zanim wstrzymanie zacznie obowiązywać. Jeśli archiwum zostało wstrzymane, w polu **Zatrzymaj bieżącą aktualizację** jest wyświetlany znacznik wyboru.
- **Wznawianie archiwizacji** — Wznów przetwarzanie wybranego archiwum, które jest obecnie wstrzymane.
- **Wycofanie** — wycofanie wybranego archiwum. Archiwum można wycofać tylko wtedy, gdy w polu **Stan** ustawiono wartość *Zakończono*. Jeśli archiwum zostało wycofane, w polu **Wycofaj** jest wyświetlany znacznik wyboru.

## <a name="extend-your-code-to-support-custom-fields"></a>Rozszerzaj kod na pola niestandardowe

Jeśli tabela `InventTrans` zawiera jedno lub więcej pól niestandardowych, może być konieczne rozszerzenie kodu w celu ich obsługi, w zależności od nazwy.

- Jeśli pola niestandardowe tabeli mają `InventTrans` takie same nazwy `InventtransArchive` jak w tabeli, oznacza to, że są mapowane w 1:1. W związku z tym można właśnie umieścić pola niestandardowe w grupie `InventoryArchiveFields` pól `inventTrans` tabeli.
- Jeśli nazwy niestandardowych pól w tabeli `InventTrans` nie są zgodne z nazwami pól w tabeli `InventtransArchive`, musisz dodać kod, aby je zamapować. Na przykład, jeśli masz pole systemowe o nazwie `InventTrans.CreatedDateTime`, musisz utworzyć pole w tabeli `InventTransArchive` o innej nazwie (np. `InventtransArchive.InventTransCreatedDateTime`) i dodać rozszerzenia do `InventTransArchiveProcessTask` i `InventTransArchiveSqlStatementHelper`, jak pokazano w poniższym przykładowym kodzie.

Poniższy przykładowy kod przedstawia przykład dodawania wymaganego rozszerzenia do klasy `InventTransArchiveProcessTask`.

```xpp
[ExtensionOf(classStr(InventTransArchiveProcessTask))]
Final class InventTransArchiveProcessTask_Extension
{

    protected void addInventTransFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTrans, ModifiedBy))
            .add(fieldStr(InventTrans, CreatedBy)).add(fieldStr(InventTrans, CreatedDateTime));

        next addInventTransFields(_selectionObject);
    }


    protected void addInventTransArchiveFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTransArchive, InventTransModifiedBy))
            .add(fieldStr(InventTransArchive, InventTransCreatedBy)).add(fieldStr(InventTransArchive, InventTransCreatedDateTime));

        next addInventTransArchiveFields(_selectionObject);
    }
}
```

Poniższy przykładowy kod przedstawia przykład dodawania wymaganego rozszerzenia do klasy `InventTransArchiveSqlStatementHelper`.

```xpp
[ExtensionOf(classStr(InventTransArchiveSqlStatementHelper))]
final class InventTransArchiveSqlStatementHelper_Extension
{
    private str     inventTransModifiedBy;  
    private str     inventTransCreatedBy;
    private str     inventTransCreatedDateTime;

    protected void initialize()
    {
        next initialize();
        inventTransModifiedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, ModifiedBy)).name(DbBackend::Sql);
        inventTransCreatedDateTime = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedDateTime)).name(DbBackend::Sql);
        inventTransCreatedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedBy)).name(DbBackend::Sql);
    }

    protected str buildInventTransArchiveSelectionFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransArchiveSelectionFieldsStatement();
        
        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransModifiedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedDateTime)).name(DbBackend::Sql));
        }

        return ret;
    }

    protected str buildInventTransTargetFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransTargetFieldsStatement();

        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransModifiedBy);
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedBy);
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedDateTime);
        }

        return ret;
    }
}
```
