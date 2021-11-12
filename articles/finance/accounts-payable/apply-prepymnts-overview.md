---
title: Automatyczne stosowanie przedpłat do faktur od dostawcy
description: W tym temacie opisano możliwości automatycznego stosowania przedpłat do faktur od dostawcy.
author: sunfzam
ms.date: 10/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: b1ea73a50f5adaa1a00c9ddfa8c983375e0d47be
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675743"
---
# <a name="automatically-apply-to-vendor-invoices"></a>Automatyczne stosowanie do faktur od dostawcy

[!include [banner](../includes/banner.md)]

W tym temacie opisano możliwości automatycznego stosowania przedpłat do faktur od dostawcy. Przedpłatę można utworzyć dla zamówienia zakupu w ramach umowy zakupu. Po otrzymaniu faktury od dostawcy przedpłata może zostać użyta do rozliczenia rozrachunków z dostawcami z faktury od dostawcy. Nowa funkcja umożliwia systemowi automatyczne używanie numerów zamówień zakupu na fakturze od dostawcy do wyszukiwania odpowiednich przedpłat podczas importowania faktury od dostawcy.

Jeśli zostaną znalezione przedpłaty i można je zastosować, wiersze zostaną dodane do istniejących wierszy faktury, aby zastosować przedpłaty. Wiersze przedpłaty nie są nigdy rozważane w trakcie procesu uzgadniania faktur.

W następujących punktach opisano, w jaki sposób są stosowane przedpłaty w przypadku różnych procesów zakupu:

- **Jedna faktura od dostawcy na zamówienie zakupu** — przedpłata na zamówieniu zakupu zostanie zastosowana do faktury od dostawcy.
- **Jedna faktura od dostawcy dla wielu zamówień zakupu** — przedpłaty na wszystkich zamówieniach zakupu zostaną zastosowane do faktury od dostawcy.
- **Wiele faktur od dostawcy na zamówienie zakupu** — przedpłata na zamówieniu zakupu zostanie zastosowana do pierwszej zaimportowanej faktury od dostawcy. Jeśli kwota przedpłaty przekracza kwotę faktury, zastosowanie przedpłaty nie powiedzie się i trzeba ręcznie zastosować przedpłatę.
- **Wiele faktur od dostawcy dla wielu zamówień zakupu** — przedpłaty na zamówieniu zakupu zostaną zastosowane do pierwszej odpowiedniej faktury. Jeśli kwota przedpłaty przekracza kwotę faktury, zastosowanie przedpłaty nie powiedzie się i trzeba ręcznie zastosować przedpłaty. Jeśli po zastosowaniu przedpłat do pierwszej faktury pozostaną inne przedpłaty, można je zastosować do kolejnych faktur.

Jeśli system będzie próbował zastosować przedpłatę, ale zastosowanie nie powiedzie się, zachowanie zależy od ustawienia opcji **Zablokuj proces automatyzacji działań kontrolnych w przypadku niepowodzenia zastosowania przedpłaty**:

- **Tak** — komunikat o błędzie „Automatyczne zastosowanie przedpłaty: Zakończone niepowodzeniem” jest dodawany do historii automatyzacji, a faktura pozostaje na liście oczekujących faktur od dostawcy. Faktura pozostanie zablokowana do czasu ręcznego zastosowania przedpłaty.

    Aby ręcznie zastosować przedpłaty, przejdź do oczekującej faktury od dostawcy. Na stronie **Szczegóły faktury** ustaw opcję **Uwzględnij w automatycznym przetwarzaniu** dla zablokowanej faktury na **Nie**. Teraz można ręcznie zastosować przedpłatę. Po zastosowaniu przedpłaty ustaw dla opcji **Uwzględnij w automatycznym przetwarzaniu** wartość **Tak**, aby faktura była automatycznie przetwarzana.

    Można także pominąć automatyczne stosowanie przedpłaty, ustawiając opcję **Uwzględnij w automatycznym przetwarzaniu** na **Nie**, a następnie ustawiając ją ponownie na **Nie**. Zostanie wyświetlony następujący komunikat: „Przedpłata już istnieje dla zamówienia zakupu. Czy chcesz zignorować tę fakturę dla wybranej faktury od dostawcy?” Wybierz opcję **Tak**. Komunikat „Zastosowanie przedpłaty zostało ręcznie ominięte” jest dodawany do historii automatyzacji, a faktura od dostawcy nie zostanie zablokowana po ponownie uruchomionym automatycznym procesie.

- **Nie** — kolejne procesy automatyzacji będą kontynuowane. Podczas rozliczania nadal można zastosować przedpłatę.
