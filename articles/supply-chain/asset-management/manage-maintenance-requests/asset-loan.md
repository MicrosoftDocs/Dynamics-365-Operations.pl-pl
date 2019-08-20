---
title: Użyczone składniki majątku
description: W tym temacie opisano sposób rejestrowania użyczonych składników majątku w Zarządzaniu składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8680241b1300aceda3280893982a1eff3d2e09e0
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847489"
---
# <a name="asset-loans"></a>Użyczone składniki majątku

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Jeśli Twoja firma otrzymuje aktywa do napraw lub prac konserwacyjnych z lokalizacji wewnętrznych lub od klientów, i jeśli tymczasowo pożyczasz aktywa do tych lokalizacji lub tym klientom, Zarządzanie składnikami majątku może śledzić użyczone składniki majątku.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Rejestracja użyczonych składników majątku w żądaniu konserwacji

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.
2. Wybierz żądanie konserwacji, aby zarejestrować użyczony składnik majątku, a następnie wybierz **Edytuj**.
3. Na stronie **żądanie** wybierz opcję **Wyślij użyczony składnik majątku**.
4. Wybierz składnik i wpisz oczekiwaną datę zwrotu.
5. Kliknij przycisk **OK**.

> [!NOTE]
> - Użyczony składnik majątku można wysłać tylko wtedy, gdy jest dostępny składnik tego samego typu.
> - Użyczany składnik majątku musi mieć stan cyklu życia pozwalający na użycie go jako użyczonego składnika majątku, np. **InStorage**. Po zarejestrowaniu użyczonego składnika majątku jego cykl życia zostanie automatycznie zaktualizowany, np. **OnLoan.**

Aby wyświetlić listę wszystkich aktywów użyczonych innym lokalizacjom lub klientom, wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Użyczony składnik majątku** \> **Wszystkie użyczone składniki majątku**. Jeśli dla składnika majątku zaznaczono pole **Zakończono**, składnik majątku został zarejestrowany jako zwrócony Twojej firmie.

![Rysunek 1](media/06-manage-maintenance-requests.png)

Na stronie **Aktywne użyczone składniki majątku** można wyświetlić listę wszystkich użyczonych składników majątku, które nie zostały jeszcze zwrócone Twojej firmie.

## <a name="register-loan-assets-as-returned"></a>Rejestrowanie użyczonych składników majątku jako zwróconych

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Użyczony składnik majątku** \> **Aktywne użyczone składniki majątku**.
2. Wybierz użyczony składnik majątku, który chcesz zarejestrować jako zwrócony, a następnie wybierz **Zwróć użyczony składnik majątku**.
3. W polu **Zwrócone** wpisz datę i godzinę.
4. Kliknij przycisk **OK**.
5. Odśwież stronę listy **Aktywne użyczone składniki majątku**. Zauważ, że użyczonego składnika majątku już na niej nie ma.
