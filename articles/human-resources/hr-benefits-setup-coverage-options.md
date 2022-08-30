---
title: Tworzenie opcji zapotrzebowania
description: W tym artykule opisano opcje objęcia świadczeniem w programie Microsoft Dynamics 365 Human Resources w przypadku wyboru uczestnika w planie lub programie świadczeń.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9c107e31e58ba1302cd02e2e82aa405dda0fdef
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336999"
---
# <a name="create-coverage-options"></a>Tworzenie opcji zapotrzebowania


Opcje ubezpieczenia określają, kto powinien być objęty ubezpieczeniem lub jaka część jest dostępna w planie ubezpieczeniowym. Na przykład w przypadku abonamentu medycznego możesz mieć opcję **Tylko pracownik**, **Pracownik + 1** i **Rodzina**. W przypadku ubezpieczenia na życie możesz zaoferować ubezpieczenie na **1 x pensja** lub **2 x pensja**.

Po zdefiniowaniu opcji zakresu świadczeń można je ponownie wykorzystać. Istnieje możliwość skojarzenia opcji z jednym lub kilkoma planami.

> [!IMPORTANT]
> Po zdefiniowaniu opcji ubezpieczenia dołącz je do typu planu świadczeń. Typ planu jest następnie kojarzony z planem lub programem świadczeń. Opcje zasięgu skojarzone z typem planu są dostępne dla wszystkich tworzonych planów tego typu.

## <a name="create-coverage-options"></a>Tworzenie opcji zapotrzebowania
1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje objęcia świadczeniem**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Opcja objęcia świadczeniem** | Unikatowa nazwa opcji objęcia świadczeniem. |
   | **Opis** | Opis opcji objęcia świadczeniem. |
   | **Kod objęcia świadczeniem** | Kody objęcia świadczeniem przypisują kwoty minimalne i maksymalne dla każdego uprawnionego typu osoby objętej. Kod objęcia świadczeniem wskazuje, kto jest objęty lub jaki jest zakres dozwolony dla typu planu. Można wyrażać kwotę pokrycia jako kwotę dolara lub procent. Na przykład:<ul><li>**Pracownik etatowy + 1** — aby się kwalifikować, pracownik etatowy musi mieć wybraną osobę zależną (Jeśli wybrano więcej niż jedną, nie kwalifikuje się on już do tego celu).</li><li>**Pracownik etatowy + Rodzina** — Aby się kwalifikować, pracownik musi mieć wybrane co najmniej dwie osoby zależne.</li></ul> |
   | **Maksymalna liczba** | Maksymalna liczba osób zależnych. |
   | **Stan** | Stan opcji objęcia świadczeniem. Jeśli stan opcji objęcia świadczeniem jest określony jako **nieaktywny**, nie można wybierać opcji objęcia w przypadku typów planów. |
   | **Procent** | Kwota procentu. To pole jest aktywne tylko wtedy, gdy w polu Kod objęcia świadczeniem wybrano % x wynagrodzenie. |
   | **Dzielnik** | Dzielnik używany w obliczeniach po wybraniu kodu objęcia świadczeniem % x wynagrodzenie. |
   | **Minimalny procent** | Minimalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem. |
   | **Maksymalny procent** | Maksymalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem. |

4. W przypadku **Opcji uprawnienia kontaktów osobistych** należy dołączyć do każdej opcji objęcia odpowiednie opcje uprawnienia do kontaktów osobistych.

5. W **Samoobsługa** wprowadź wartości w następujących polach:

   | Pole | Opis |
   | --- | --- |
   | **Zezwalaj na kwotę wkładu pracownika etatowego** | Określa, czy zezwalać pracownikom na modyfikowanie kwoty wkładu w samoobsłudze świadczeń podczas wybierania świadczeń. Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty udziału, jaką pracownik wprowadzi w ramach samoobsługi świadczeń. |
   | **Zezwalaj na kwotę objęcia świadczeniem pracownika etatowego** | Określa, czy zezwalać pracownikom na modyfikowanie kwoty uprawnienia w samoobsłudze świadczeń podczas wybierania świadczeń. Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty uprawnienia, jaką pracownik wprowadzi w ramach modułu samoobsługowego pracownika. |

6. Wybierz opcję **Zapisz**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
