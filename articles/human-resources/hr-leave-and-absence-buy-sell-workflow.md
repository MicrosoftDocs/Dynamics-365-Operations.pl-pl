---
title: Tworzenie przepływu pracy zakupu i sprzedawania urlopów
description: W programie Dynamics 365 Human Resources można utworzyć przepływ pracy wniosków o zakup i sprzedaż urlopów, aby konsekwentnie zarządzać wnioskami urlopowymi.
author: twheeloc
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aaed459c74ce79226a8e4c6276fe210674832d10
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692178"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Tworzenie przepływu pracy zakupu i sprzedawania urlopów


>[!Important]
>Funkcjonalność opisana w tym temacie jest obecnie dostępna dla klientów samodzielnej wersji Dynamics 365 Human Resources. Część lub całość tej funkcjonalności będzie dostępna w ramach przyszłego wydania infrastruktury Finance po wydaniu wersji Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W programie Dynamics 365 Human Resources można utworzyć przepływ pracy, aby spójnie zarządzać wnioskami o sprzedaż i zakup urlopów. Przepływ pracy **Zakup i sprzedaż urlopu** umożliwia:

- Definiowanie zadań
- Określanie, kto musi wykonać te zadania
- Określanie, kto może zatwierdzać lub odrzucać wnioski

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>Tworzenie przepływu pracy zakupu i sprzedawania urlopów

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Przepływy pracy modułu zasobów ludzkich**.

3. Wybierz kolejno opcje **Nowy** i **Wniosek o zakup i sprzedaż urlopu**. 

4. Gdy pojawi się okno komunikatu **Otworzyć ten plik?**, kliknij przycisk **Otwórz** i zaloguj się przy użyciu firmowych poświadczeń.

5. Za pomocą edytora przepływu pracy utwórz przepływ pracy dla wniosków urlopowych. Więcej informacji na temat pracy z przepływami pracy zawiera temat [Omówienie tworzenia przepływów pracy](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Elementy danych przepływu pracy wniosków o urlopy i nieobecności

Poniższe elementy danych mogą służyć do tworzenia warunkowych lub automatycznych zatwierdzeń w przepływach pracy dotyczących wniosków o zakup lub sprzedaż urlopów:

- **Ilość**
- **Zasady zakupu i sprzedaży urlopu**
- **Firma**
- **Utworzony przez**
- **Data i godzina utworzenia**
- **Data końcowa**
- **Typ urlopu**
- **Zmodyfikowane przez**
- **Data i godzina modyfikacji**
- **Identyfikator wniosku**
- **Rozpoczęcie**
- **Stan** 
- **Data przesłania**
- **Przesłano przez**
- **Przesłane przez dział kadr**
- **Przesłane przez menedżera**
- **Przesłane w imieniu**
- **Pracownik**

## <a name="workflow-examples"></a>Przykłady przepływów pracy

Poniższe przykłady pokazują, jak można tworzyć różne typy warunków przepływu pracy za pomocą następujących elementów danych:

- Opcje **Przesłanych przez dział kadr** i **Przesłane przez menedżera** są używane w ramach akcji automatycznej w celu automatycznego zatwierdzania wniosków o zakup lub sprzedaż urlopu przesyłanych przez te role w imieniu pracowników. Aby uzyskać więcej informacji o akcjach automatycznych, zobacz temat [Konfigurowanie procesów zatwierdzania w przepływie pracy](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- **Typ urlopu** jest używany w instrukcji warunkowej lub akcji automatycznej do kontrolowania sposobu, w jaki przepływ pracy kieruje wnioski do określonych typów urlopów.

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)<br>
[Zarządzaj zasadami zakupu i sprzedaży urlopu](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)<br>
[Kupuj i sprzedawaj urlop](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
