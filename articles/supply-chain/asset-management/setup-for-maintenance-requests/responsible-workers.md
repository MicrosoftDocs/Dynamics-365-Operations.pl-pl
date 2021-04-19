---
title: Odpowiedzialni konserwatorzy
description: W tym temacie wyjaśniono, jak konfigurować odpowiedzialnych konserwatorów w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1330aa04a57809ff34dcca9791f8fb0a93c8d71
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808455"
---
# <a name="responsible-maintenance-workers"></a>Odpowiedzialni konserwatorzy

[!include [banner](../../includes/banner.md)]

 

Odpowiedzialni konserwatorzy mogą być powiązani z typami składników majątku, składnikami majątku, lokalizacjami czynności konserwacyjnych, kategoriami typów zadań konserwacji, typami zadań konserwacji, wariantami typów zadań konserwacji oraz profesjami. Mogą oni być używane na zleceniach pracy i żądaniach konserwacyjnych w celu wskazania preferencji odnośnie do konserwatorów, którzy powinni być odpowiedzialni za zlecenie pracy. (Jednak konserwatorzy nie są koniecznie tymi samymi pracownikami, którzy mają zamiar wykonać zlecenie pracy). Użycie tej funkcji jest opcjonalne. Można na przykład wybrać w ten sposób odpowiedzialnych konserwatorów lub grupy pracowników do konkretnych typów pracy lub obszarów pracy.

Podczas cyklu życia zlecenia pracy lub cyklu realizacji żądania konserwacji odpowiedzialni konserwatorzy mogą być zmieniani lub aktualizowani. Taka zmiana lub aktualizacja może być związana na przykład ze zmianą stanu cyklu życia żądania konserwacji lub cyklu życia zlecenia pracy.

Ustawienia na stronie **Odpowiedzialni konserwatorzy** *nie* są używane podczas planowania zleceń pracy.

> [!NOTE]
> W module Zarządzanie środkami trwałymi można również konfigurować *preferowanych* konserwatorów, którzy mogą być przydzielani do zleceń pracy w planowaniu zlecenia pracy.

Aby można było skonfigurować odpowiedzialnych konserwatorów, należy skonfigurować pracowników oraz grupy konserwatorów, które powinny być dostępne do wybrania. Aby uzyskać informacje na temat konfiguracji pracowników i grup konserwatorów, zobacz temat [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-responsible-maintenance-workers"></a>Ustawienia odpowiedzialnych konserwatorów

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Pracownicy** \> **Odpowiedzialni konserwatorzy**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. Najpierw utwórz konfigurację odpowiedzialnego konserwatora lub grupy odpowiedzialnych konserwatorów, w której trzeba ustawić tylko pole **Grupa odpowiedzialnych konserwatorów** i/lub pole **Odpowiedzialny pracownik**. Pozostaw pola zostaw puste. Ta domyślna konfiguracja będzie używana podczas planowania zleceń pracy, jeśli żadna inna określona kombinacja nie pasuje do zawartości zlecenia pracy.

    > [!NOTE]
    > Podczas tworzenia żądania konserwacji, gdy odpowiedzialny konserwator lub grupa odpowiedzialnych konserwatorów są dostępne do wybrania na stronie **Wszystkie żądania konserwacji**, moduł Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy odpowiedzialnych konserwatorów, aby sprawdzić, czy są możliwe dopasowania. W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową. Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza dopasowanie dla pola **Profesja**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Wariant typu zadania konserwacji**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Wariant typu zadania konserwacji** itd. Jak widać w układzie strony, to zachowanie to oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej w celu dopasowania (najpierw **Profesja**, następnie **Wariant typu zadania konserwacji**, następnie **Typ zadania konserwacji**, następnie **Kategoria typu zadania konserwacji**, następnie **Lokalizacja czynności konserwacyjnych**, następnie **Składnik majątku** i na końcu **Typ składnika majątku**). Jeśli nie uda się znaleźć dopasowania, jest używany rekord domyślny, który nie ma zaznaczeń w tych siedmiu polach.

Na poniższej ilustracji pokazano przykład strony **Odpowiedzialni konserwatorzy**.

![Strona Odpowiedzialni konserwatorzy](media/08-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]