---
title: Tworzenie opcji zapotrzebowania
description: Opcje zapotrzebowań w Microsoft Dynamics 365 Human Resources to poziomy zapotrzebowań na wybory uczestnika w planie lub programie świadczeń, takie jak tylko pracownik etatowy dla planu medycznego, lub podwójna wartość wynagrodzenia dla planu ubezpieczenia na życie.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092713"
---
# <a name="create-coverage-options"></a>Tworzenie opcji zapotrzebowania

[!include [banner](includes/preview-feature.md)]

Opcje zapotrzebowań w Microsoft Dynamics 365 Human Resources to poziomy zapotrzebowań na wybory uczestnika w planie lub programie świadczeń, takie jak tylko pracownik etatowy dla planu medycznego, lub podwójna wartość wynagrodzenia dla planu ubezpieczenia na życie. Po zdefiniowaniu opcji świadczeń z tytułu świadczenia można używać ponownie, a także kojarzyć opcję z jednym lub kilkoma planami.

Po zdefiniowaniu opcji zapotrzebowania należy dołączyć opcje zapotrzebowania do typu planu świadczeń. Typ planu jest następnie kojarzony z planem lub programem świadczeń. Opcje zapotrzebowania skojarzone z typem planu będą dostępne dla wszystkich planów utworzonych przy użyciu tego typu planu. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje objęcia świadczeniem**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Opcja objęcia świadczeniem** | Unikatowa nazwa opcji objęcia świadczeniem. |
   | **Opis** | Opis opcji objęcia świadczeniem. |
   | **Kod objęcia świadczeniem** | Kody objęcia świadczeniem przypisują kwoty minimalne i maksymalne dla każdego uprawnionego typu osoby objętej. Kod objęcia świadczeniem wskazuje, kto jest objęty lub jaki jest zakres dozwolony dla typu planu. Można wyrażać kwotę pokrycia jako kwotę dolara lub procent. Na przykład:</br></br>- **EMP + 1** — aby się kwalifikować, pracownik etatowy musi mieć wybraną osobę zależną (Jeśli wybrano więcej niż jedną, nie kwalifikuje się on już do tego celu).</br></br>- **EMP + Rodzina** — Aby się kwalifikować, pracownik musi mieć wybrane co najmniej dwie osoby zależne. |
   | **Maksymalna liczba** | Maksymalna liczba osób zależnych. |
   | **Stan** | Stan opcji objęcia świadczeniem. Jeśli stan opcji objęcia świadczeniem jest określony jako nieaktywny, nie można wybierać opcji objęcia w przypadku typów planów. |
   | **Procent** | Kwota procentu. To pole jest aktywne tylko wtedy, gdy w polu Kod objęcia świadczeniem wybrano % x wynagrodzenie. |
   | **Dzielnik** | Dzielnik używany w obliczeniach po wybraniu kodu objęcia świadczeniem % x wynagrodzenie. |
   | **Minimalny procent** | Minimalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem. |
   | **Maksymalny procent** | Maksymalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem. |

4. W przypadku **Opcji uprawnienia kontaktów osobistych** należy dołączyć do każdej opcji objęcia odpowiednie opcje uprawnienia do kontaktów osobistych.

5. W **Samoobsługa** wprowadź wartości w następujących polach:

   | Pole | Opis |
   | --- | --- |
   | **Zezwalaj na kwotę wkładu pracownika etatowego** | Określa, czy zezwalać pracownikom na modyfikowanie kwoty wkładu w samoobsłudze świadczeń podczas wybierania świadczeń. Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty udziału, jaką pracownik wprowadzi w ramach modułu samoobsługowego. |
   | **Zezwalaj na kwotę objęcia świadczeniem pracownika etatowego** | Określa, czy zezwalać pracownikom na modyfikowanie kwoty uprawnienia w samoobsłudze świadczeń podczas wybierania świadczeń. Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty uprawnienia, jaką pracownik wprowadzi w ramach modułu samoobsługowego pracownika. |

6. Wybierz opcję **Zapisz**. 
