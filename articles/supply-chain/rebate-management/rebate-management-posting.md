---
title: Konfiguracja księgowania dla modułu Zarządzanie rabatami
description: W tym temacie opisano sposób konfigurowania danych do profili księgowania. Profile księgowania służą do określania wpisów księgowania w wierszach obliczeń zarządzania rabatami.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: e79feb567a48d08a9063bf20cface3c5c7fe8ecc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831753"
---
# <a name="rebate-management-posting-setup"></a>Konfiguracja księgowania dla modułu Zarządzanie rabatami

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Profile księgowania służą do określania wpisów księgowania w wierszach obliczeń zarządzania rabatami. Profil księgowania wybrany w nagłówku umowy dotyczy wszystkich wierszy umowy.

Ta funkcja działa między firmami. Można określić firmę, dla których będą naliczane rezerwy i przez które będą spłacone roszczenia. Można również ustawić różne konta debetowe i konta księgowania odpisów według źródłowej firmy księgowej.

Aby skonfigurować profile księgowania zarządzania rabatami dla odbiorców i dostawców, przejdź do **Zarządzania rabatami \> Ustawienia księgowania zarządzania rabatami \> Profile księgowania zarządzania rabatami**. Strona **Profile księgowania zarządzania rabatami** zawiera okienko listy, w których są widać wszystkie istniejące profile. Możesz użyć przycisków w okienku akcji, aby dodać profile do listy lub je usunąć.

Pozostałe sekcje tego tematu zawierają opis sposobu używania dostępnych pól podczas tworzenia lub edytowania profilu.

## <a name="posting-profile-header"></a>Nagłówek profilu księgowania

W poniższej tabeli opisano ustawienia dostępne w sekcji nagłówka każdego profilu księgowania zarządzania rabatami.

| Pole | opis |
|---|---|
| Profil księgowania | Wprowadź unikatową nazwę profilu. |
| opis | Umożliwia wprowadzanie opisu profilu. |
| Moduł | Umożliwia wybranie typu rabatów i tantiem, z które jest skojarzony profil (*Odbiorca* lub *Dostawca*). |
| Typ | Wybierz typ profilu (*Rabat* lub *Tantiemy*). |
| Typ płatności | <p>Pole to określa format zaksięgowanej produkcji rabatu.<p><p>Gdy w polu **Typ** zostanie ustawiona wartość *Rabat*, dostępne są następujące wartości:</p><ul><li>*Brak* — nie istnieje domyślny typ księgowania. W związku z tym podczas przetwarzania należy określić jego typ.</li><li>*Płać z zastosowaniem rozrachunków z dostawcami* – Po zaksięgowaniu rabatu zostanie utworzona faktura dostawcy dla dostawcy przekazów ustawiona dla tego odbiorcy rabatu.</li><li>*Potrącenia od odbiorcy* – W momencie zaksięgowania rabatu jest tworzony arkusz potrąceń od odbiorcy dla tego odbiorcy rabatu.</li><li>*Tax invoice customer deductions* – Po zaksięgowaniu rabatu tworzona jest faktura niezależna dla odbiorcy korzystającego z rabatu.</li><li>*Wydatki w handlu* – W momencie zaksięgowania rabatu jest tworzony arkusz potrąceń od odbiorcy dla tego odbiorcy rabatu.</li><li>*Raportowanie* – W momencie zaksięgowania rabatu jest tworzony arkusz potrąceń od odbiorcy dla tego odbiorcy rabatu.</li></ul><p>Gdy w polu **Typ** zostanie ustawiona wartość *Tantiema*, dostępne są następujące wartości:</p><ul><li>*Brak* — nie istnieje domyślny typ księgowania. W związku z tym podczas przetwarzania należy określić jego typ.</li><li>*Płać z zastosowaniem rozrachunków z dostawcami* – Podczas księgowania rabatu tworzona jest faktura dostawcy dla konta dostawcy rabatu.</li><li>*PłaćRaporowanie* – Podczas księgowania rabatu tworzona jest faktura dostawcy dla konta dostawcy rabatu.</li></ul><p>Aby uzyskać więcej informacji, zobacz sekcję [Typy płatności](#payment-types) poniżej. |
| Firma | Można wybrać firmę, dla których będą naliczane rezerwy i przez które będą spłacone roszczenia. |

### <a name="payment-types"></a>Typy płatności

W poniższej tabeli podsumowano wpływ różnych ustawień pola **Typ płatności** na miejsca, w których są księgowane płatności. Płatności mogą być księgowane na koncie odbiorcy, koncie dostawcy lub koncie przelewu, w zależności od transakcji docelowej i typu rabatu.

| Typ płatności | Typ transakcji docelowej | Typ rabatu | Płatność do (konto fakturowania) |
|---|---|---|---|
| Płać z modułu rozrachunków z dostawcami | Arkusz faktur od dostawców | Rabat dla odbiorcy | Konto dostawcy przelewu odbiorcy |
| Płać z modułu rozrachunków z dostawcami | Arkusz faktur od dostawców | Lojalność klienta | Konto dostawcy |
| Płać z modułu rozrachunków z dostawcami | Arkusz faktur od dostawców | Rabat dostawcy | Konto dostawcy |
| Potrącenia od odbiorcy | Arkusz dzienny | Rabat dla odbiorcy | Konto odbiorcy |
| Potrącenia odbiorcy z faktury podatkowej | Faktura niezależna | Rabat dla odbiorcy | Konto odbiorcy |
| Wydatki handlowe | Arkusz dzienny | Rabat dla odbiorcy | Konto odbiorcy |
| Raportowania | Arkusz dzienny | Rabat dla odbiorcy | Konto odbiorcy |
| Raportowania | Arkusz faktur od dostawców | Lojalność klienta | Konto dostawcy |
| Raportowania | Arkusz faktur od dostawców | Rabat dostawcy | Konto dostawcy |

> [!NOTE]
> W przypadku skonfigurowania [umów zarządzania rabatami](rebate-management-deals.md) należy uwzględnić następujące kwestie:
>
> - W przypadku umów, w których w polu **Uzgadnianie do** jest ustawiona wartość *Umowa*, nie można używać dynamicznego konta umowy podczas księgowania. Musisz użyć określonego konta odbiorcy lub dostawcy.
> - W przypadku transakcji, w których w polu **Uzgadnianie do** jest ustawiona wartość *Wiersz*, można użyć profilu księgowania, który jest przeciwstawny do dynamicznego konta umowy w wierszu umowy, ponieważ odbiorca jest ustawiony dla każdego wiersza umowy.

## <a name="posting-fasttab"></a>Skrócona karta Księgowania

W poniższej tabeli opisano pola dostępne w karcie **Księgowanie** każdego profilu księgowania zarządzania rabatami.

| Pole | opis |
|---|---|
| Typ kredytu | Określ, czy ma być księgowane po stronie kredytowej konto księgowe, czy konto odbiorcy lub dostawcy. |
| Konto kredytowe | Konto, na którym są księgowane kwoty po stronie kredytowej w przypadku rezerw rabatowych. To konto będzie również używane jako konto debetowe podczas zaksięgowania rabatu po stronie kredytowej odbiorcy. |
| Nazwa arkusza<br>(W sekcji **Prowizje**) | Wybierz nazwę arkusza, który ma być rejestrowany zaksięgowane świadczenie. |
| Typ | Wybierz, czy zaksięgować rabat na koncie księgowym, czy na odbiorcę lub dostawcę. Jeśli pole **Typ płatności** w nagłówku jest ustawione na *potrącenia od odbiorcy z faktury podatkowej*, to pole jest ustawione na *Odbiorca/Dostawca*. |
| Korzystanie z konta źródłowego | <p>Należy wybrać jedną z następujących opcji:</p><ul><li>*Brak* — w przypadku wybrania tej wartości należy określić konto w polu **Konto rabatowe**.</li><li>*Konto umowy* — należy użyć konta odbiorcy lub dostawcy określonego w wierszu rabatu. Tę wartość można wybrać tylko w przypadku transakcji, w których w polu **Uzgodnij do** jest ustawiona wartość *Wiersze* i umowy, w których w polu **Kod konta** ustawiono wartość *Tabela*. Nie ma ono zastosowania do profilów księgowania tantiem odbiorcy.</li></ul> |
| Konto rabatu | Konto, na które zostaną zaksięgowane rzeczywiste wydatki związane z rabatami. |
| Nazwa arkusza<br>(W sekcji **Zarządzanie rabatami**) | Umożliwia wybór nazwy arkusza służącego do zaksięgowania faktury korygowej dla kwoty rabatu dla odbiorcy. Jeśli pole **Typ płatności** w nagłówku jest ustawione na *potrącenia od odbiorcy z faktury podatkowej*, to pole jest niedostępne. |
| Grupa podatków dla pozycji | Określ, czy rabat podlega opodatkowaniu. |
| Nazwa arkusza<br>(W sekcji **Odpis**) | Jeśli zaksięgowany rabat nie jest równy prowizji, różnica może zostać odpisana. Wybierz nazwę arkusza, który ma być rejestrowany zaksięgowany odpis. |

## <a name="posting-by-company-fasttab"></a>Księgowanie według skróconej karty firmy

Skrócona karta **Księgowanie według firm** w każdym profilu księgowania w zarządzaniu rabatami umożliwia określenie konta księgowania używanego w siatce przez poszczególne firmy (firmy).

Użyj przycisków na pasku narzędzi, aby dodać firmy do siatki i je usunąć. Po każdym dodaniu wiersza do siatki należy użyć pola **Firma**, aby określić firmę dla tego wiersza. Pole **Nazwa** jest ustawiane automatycznie.

Wybierz wiersz dla każdej firmy, a następnie wprowadź następujące informacje, używając pól poniżej siatki:

- **Typ debetu** – Określ, czy ma być księgowane po stronie kredytowej konto księgowe, czy konto odbiorcy lub dostawcy.
- **Konto debetowe** — Służy do wprowadzania konta, na którym księgowana jest kwota po stronie debetowej w przypadku rezerw w przypadku rabatów.
- **Konto główne** — umożliwia wybór konta głównego dla odpisów.
