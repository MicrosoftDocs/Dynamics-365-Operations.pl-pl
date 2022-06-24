---
title: Omówienie profili księgowania
description: W tym artykule opisano sposób, w jaki profile księgowania są używane w aplikacjach Microsoft Dynamics 365.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7ef3be13e82ff3722fc81247b5cd581b0b571b0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876132"
---
# <a name="posting-profiles-overview"></a>Omówienie publikowania profili

W aplikacjach Finanse i Operacje termin *Profile księgowania* służy do opisywania konfiguracji sterujących konwersją kont księgi podrzędnej na konta główne, dzięki czemu można ich używać w transakcjach księgowanych w księdze głównej. Na przykład kontrolują one sposób konwersji odbiorcy na konto główne rozrachunków z odbiorcami podczas zaksięgowania faktury.

Niektóre moduły i funkcje zawierają stronę, która zawiera słowo „Profil księgowania” w nazwie (na przykład **Profil księgowania odbiorcy** lub **Profil księgowania dostawcy**). Ponadto w niektórych modułach jest dostępnych wiele opcji konfigurowania księgowania w księdze dla transakcji generowanych z księgi podrzędnej. Na przykład w module **Kontrola produkcji** można skonfigurować księgowanie według grupy produkcji, zasobu lub grupy zasobów.

Należy zauważyć, że w przypadku wielu typów transakcji istnieją alternatywne profile księgowania: definicje księgowania. Dla obsługiwanych dokumentów można używać definicji księgowania zamiast profili księgowania do klasyfikacji kont głównych i wymiarów finansowych dla zapisów księgowych. Jeśli zamierzasz używać przyszłych zobowiązań wiążących lub przyszłych zobowiązań niewiąjących, do zdefiniowania kont wpisów księgowych jest wymagana definicja księgowania.

Przed skonfigurowaniem profilów księgowania, definicji księgowania lub kont dla **transakcji automatycznych** należy skonfigurować konto plan kont na stronie **Księga** w firmie, którą chcesz skonfigurować.

## <a name="posting-types"></a>Typy księgowania

W aplikacjach Finanse i Operacje typ księgowania służy do definiowania ogólnej kategorii debetu lub kredytu. Ta kategoria jest niezależna od konta głównego w księdze głównej. Istnieją typy księgowania dla każdego debetu lub kredytu w księdze głównej.

Jeden załącznik może mieć jeden lub więcej typów księgowania. Na przykład transakcja księgowana za pośrednictwem arkusza księgi głównej, dla której ustawieniem konta i konta przeciwstawnego jest **Księga**, będzie mieć typ księgowania **Arkusz księgi** zarówno dla księgowania debetowego, jak i kredytowego. Natomiast faktura od dostawcy będzie mieć wiele typów księgowania. Te typy księgowania będą zawierać jeden wiersz dla salda dostawcy i dodatkowe wiersze dla zapisu przeciwstawne, takie jak **arkusz księgi**.

Typ księgowania można wyświetlić w polu **Typ księgowania** na karcie **Ogólne** na stronie **Transakcje na załączniku**.

> [!TIP]
> Paska narzędzi **Personalizacja** można użyć w celu dodania pola **Typ księgowania** do siatki na karcie **Przegląd** lub przeniesienia go. W ten sposób można ułatwić dostęp do tego pola i wyświetlać je podczas wyświetlania załączników.

## <a name="detail-settings-for-a-posting-profile"></a>Szczegółowe ustawienia profilu księgowania 

Podczas konfigurowania profilów księgowania pole **Kod konta** określa poziom ustawienia. W poniższej tabeli przedstawiono dostępne opcje: **Tabela**, **Grupa** i **Wszyscy**. Uzgadnianie kończy się po pierwszym dopasowaniu, a zamówienie jest z poziomu najbardziej konkretnego do najmniej konkretnego. Chociaż w niektórych przypadkach pole **Kod konta** może mieć nieco inną nazwę, zachowanie i funkcja tego pola pozostają takie same. Profil księgowania zapasów zawiera na przykład pole **Kod towaru** i **Kod konta**. Oba pola mają wartości **Tabela**, **Grupa** i **Wszystkie**.

Jeśli pole **Konto główne** jest puste w przypadku profilu księgowania, a konto główne nie zostało skonfigurowane na stronie **Konta do transakcji automatycznych** lub na stronie dotyczącej konkretnego modułu lub funkcji , otrzymasz komunikat o błędzie podczas księgowania transakcji korzystającej z typu księgowania. Zazwyczaj komunikat będzie mieć treść „Nie można odnaleźć konta dla \[typu księgowania\]”.

### <a name="table-value"></a>Wartość tabeli

Wartość **tabeli** odwołuje się do rekordu głównego skojarzonego z profilem księgowania. Każdy rekord tabeli jest specyficzny dla jednej wartości. Ta wartość jest określana w polu wyświetlanym po polu **Kod konta**. Zazwyczaj to pole nosi nazwę **Konto** lub **Konto/Numer grupy**. Dokładna nazwa różni się w zależności od strony, na której się pojawia.

Jeśli na przykład użytkownik pracuje z profilem księgowania odbiorcy, wartość **Tabela** reprezentuje określonego odbiorcy. W przypadku wybrania opcji **Tabela** w polu **Kod konta** wybierz numer odbiorcy w polu **Numer konta/grupy**.

Wartość **Tabeli** reprezentuje najbardziej konkretny typ rekordu. System zawsze używa tej wartości, nawet jeśli został skonfigurowany inny rekord, w którym zaznaczono wartość **Grupa** lub **Wszystkie**. Ta wartość zastępuje również wszystkie wartości utworzone jako wartości domyślne na stronie **Konta transakcji automatycznych**.

Nie zaleca się używania wartości **tabeli** jako podstawowego mechanizmu zarządzania profilami księgowania, ponieważ problemy z jakością danych mogą wystąpić, jeśli dla każdego rekordu danych głównych zostanie zachowany oddzielny profil księgowania. Ponadto obsługa i uzgadnianie oddzielnego profilu księgowania dla każdego rekordu danych głównego jest trudne. Zamiast tego tej wartości należy używać do zarządzania wyjątkami w profilach księgowania.

### <a name="group-value"></a>Wartość grupy

Wartość **Grupa** odwołuje się do rekordu grupowania obsługiwanego przez rekord główny skojarzony z profilem księgowania. Każdy rekord grupy jest specyficzny dla jednej wartości. Ta wartość jest określana w polu wyświetlanym po polu **Kod konta**. Zazwyczaj to pole nosi nazwę **Konto** lub **Konto/Numer grupy**. Dokładna nazwa różni się w zależności od strony, na której się pojawia.

Wartość **Grupa** wymaga, aby najpierw skonfigurować grupę i połączyć ją z co najmniej jednym rekordem konta. Wartość **Grupa** jest mniejsza niż wartość w **tabeli**, ale bardziej specyficzna niż **wartość Wszystkie**. Jeśli dla tabeli nie skonfigurowano żadnego rekordu, system będzie próbował znaleźć rekord dla grupy, do której należy ten rekord.

Na przykład, jeśli pracujesz z profilem księgowania odbiorcy i wybierzesz pozycję **Grupa** w polu **Kod konta**, musisz wybrać grupę odbiorcy w polu **Numer konta/grupy**. Należy wstępnie zdefiniować grupy klientów na stronie **Grupa klientów** i określić grupę podczas tworzenia odbiorcy.

Zaleca się, aby w przypadku danego typu księgowania śledzić wiele kont głównych, zaleca się użycie wartości **Grupa**. Na przykład są trzy główne konta handlowe rozrachunków z odbiorcami: jedno dla zwykłych odbiorców, jedno dla pracowników i jedno dla sprzedaży międzyfirmowej. W takim przypadku zaleca się utworzenie trzech grup odbiorców w celu segmentacji odbiorców. Następnie przymapuj każdą grupę klientów do prawidłowego konta głównego w profilu księgowania odbiorcy. W poniższej tabeli przedstawiono trzy grupy klientów w tym przykładzie.

| Grupa odbiorców | Nazwa | Opis |
|----------------|------|-------------|
| EXT | Odbiorca zewnętrzny | Ta grupa jest używana dla wszystkich standardowych odbiorców zewnętrznych. |
| EMP | Pracownicy etatowi | Ta grupa jest używana dla wszystkich pracowników, którzy kupują zakupy z danej organizacji. |
| INT | Międzyfirmowa sprzedaż | Ta grupa jest używana dla wszystkich międzyfirmowych kont odbiorcy używanych z integracyjnymi zamówieniami sprzedaży i zakupu. |

W profilu księgowania zostaną ustawione trzy wiersze. W każdym wierszu należy wybrać wartość **Grupa** i powiązane konto główne.

### <a name="all-value"></a>Wszystkie wartości

Wartość **Wszystkie** wskazuje, że ustawienia dotyczą wszystkich rekordów. Jeśli w polu **Kod konta** zostanie zaznaczyna wartość **Wszystkie**, pole **Numer konta/grupa** jest niedostępne i nie można wybrać konkretnego rekordu, do który ma zostać zastosować konfigurację.

Wartość **Wszystkie** jest najmniej określoną wartością. Jest używane tylko wtedy, gdy system nie może znaleźć dopasowania dla **wartości Tabela** lub **Grupa**. Wybierz opcję **Wszystkie**, jeśli dla określonego typu księgowania jest dostępne tylko jedno konto główne.

Na przykład podczas pracy z profilem księgowania odbiorcy konta główne określone przez użytkownika mają zastosowanie do wszystkich innych odbiorców i grup odbiorców, które nie mają rekordu dla określonej tabeli (odbiorcy) lub grupy (grupy odbiorców).

### <a name="category"></a>Kategoria

Profile księgowania zapasów mają dodatkową wartość, która jest specyficzna dla kategorii sprzedaży lub zaopatrzenia. Ta wartość przypomina wartość **Tabela**, ponieważ dotyczy tylko określonej kategorii sprzedaży lub zaopatrzenia.

### <a name="default-value"></a>Wartość domyślna

Jeśli nie utworzysz rekordu dla typu księgowania w profilu księgowania, w którym pole **Kod konta** ma wartość **Wszystkie**, a system nie może odnaleźć pasującego rekordu profilu księgowania dla wartości **grupa** lub **tabela**, system przywróci wartość domyślną, która może zostać określona na stronie **Konta dla transakcji automatycznych**. Aby uzyskać więcej informacji, zobacz [temat Konta dla transakcji automatycznych](accounts-for-auto-transactions.md).

## <a name="clearing-accounts"></a>Konta rozliczeniowe

Termin *konto rozliczeniowe* jest często używany w księgowości. Niektóre typy księgowania w aplikacjach Microsoft Dynamics 365 są kontami rozliczeniowymi. Innymi słowy, saldo konta jest wyczyszcone lub wycofane w momencie zaksięgowania innej transakcji. Na przykład podczas księgowania przyjęcia produktu z zamówienia zakupu suma szacowanych kosztów produktów plus podatek i wszelkie opłaty w wierszach zamówienia zakupu jest księgowana w typie księgowania naliczania zakupu jako zobowiązanie. Później, po zafakturowanie zamówienia zakupu, saldo jest cofane z typu księgowania naliczania zakupu i przenoszone na konto handlowe Rozrachunki z dostawcami.

## <a name="additional-resources"></a>Dodatkowe zasoby

Wiele modułów w Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce i Dynamics 365 Project Operations ma profil księgowania lub dodatkowe konfiguracje, które kontrolują sposób działania księgowania w księdze głównej. Aby dowiedzieć się więcej o profilach księgowania i konfiguracjach księgowania w poszczególnych modułach, należy skorzystać z następujących tematów:

- [Konta dla transakcji automatycznych](accounts-for-auto-transactions.md)
- [Menedżer ds. księgowości z dostawcami](accts-payble-posting.md)
- [Księgowanie na kontach odbieralnych](accts-recvble-posting.md)
- [Księgowość dotycząca wynajmu składników majątku](../asset-leasing/set-up-lease-posting-accts.md)
- Księgowanie zarządzania składnikami aktywów (wkrótce)
- Parametry modułu Zarządzanie gotówką i bankami (wkrótce)
- Konta księgowania przesądów walut (wkrótce)
- Księgowanie zarządzania wydatkami (wkrótce)
- [Profil księgowania środków trwałych](../fixed-assets/tasks/set-up-fixed-asset-posting-profiles.md)
- Księgowanie księgowania międzyfirmowego (wkrótce)
- Profil księgowania zapasów (wkrótce)
- [Księgowość dot. kosztów z wyładunkiem](../../supply-chain/landed-cost/costing-parameters-setup.md)
- [Omówienie definicji księgowania](posting-definitions.md)
- Księgowanie kontroli produkcji (wkrótce)
- Zarządzanie projektami i księgowanie księgowe (wkrótce)
- Księgowanie zarządzania usługami (wkrótce)
- Księgowanie podatku (wkrótce)
- Księgowanie w czasie i frekwencji (wkrótce)
- Księgowanie zarządzania transportem (wkrótce)
- Profile publikowania zarządzania rabatami (wkrótce)
