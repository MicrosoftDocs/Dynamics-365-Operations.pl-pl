---
title: Przełączanie się między projektami dostawcy
description: W tym temacie opisano sposób przełączania integracji danych dostawcy między aplikacjami Finance and Operations i Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: d2c22123d5f05945b34eb107c5b912852aec387a
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744472"
---
# <a name="switch-between-vendor-designs"></a>Przełączanie się między projektami dostawcy

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a>Przepływ danych dostawcy 

W przypadku wybrania opcji używania tabeli **Konto** do przechowywania dostawców typu **Organizacja** i tabeli **Kontakt** do przechowywania dostawców typu **Osoba**, należy skonfigurować następujące przepływy pracy. W przeciwnym razie ta konfiguracja nie jest wymagana.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Użycie rozszerzonego projektu dostawcy dla dostawców typu Organizacji

Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy. Zostanie utworzony przepływ pracy dla każdego szablonu.

+ Tworzenie dostawców w tabeli kont
+ Tworzenie dostawców w tabeli dostawców
+ Aktualizowanie dostawców w tabeli kont
+ Aktualizowanie dostawców w tabeli dostawców

Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:

1. Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców w tabeli kont**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla tabeli **konta**.

    ![Proces przepływu pracy Tworzenie dostawców w tabeli kont](media/create_process.png)

2. Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Aktualizowanie dostawców w tabeli kont**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla tabeli **konta**.
3. Utwórz nowy proces przepływu pracy dla tabeli **Konto** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców w tabeli dostawców**.
4. Utwórz nowy proces przepływu pracy dla tabeli **Konto** i wybierz szablonu procesu przepływu pracy **Aktualizowanie dostawców w tabeli dostawców**.
5. Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika. Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.

    ![Przycisk Konwertuj na przepływ pracy w tle](media/background_workflow.png)

6. Umożliwia aktywowanie przepływów pracy utworzonych dla tabel **Konto** i **Dostawca** w celu rozpoczęcia używania tabeli **Konta** do przechowywania informacji o dostawcy dla typu **Organizacja**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Użycie rozszerzonego projektu dostawcy dla dostawców typu Osoby

Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy. Zostanie utworzony przepływ pracy dla każdego szablonu.

+ Tworzenie dostawców typu Osoba w tabeli dostawców
+ Tworzenie dostawców typu Osoba w tabeli kontaktów
+ Aktualizowanie dostawców typu Osoba w tabeli kontaktów
+ Aktualizowanie dostawców typu Osoba w tabeli dostawców

Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:

1. Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców typu Osoba w tabeli kontaktów**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla tabeli **Kontakt**.
2. Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Aktualizowanie dostawców typu Osoba w tabeli kontaktów**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla tabeli **Kontakt**.
3. Utwórz nowy proces przepływu pracy dla tabeli **Kontakt** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców typu Osoba w tabeli dostawców**.
4. Utwórz nowy proces przepływu pracy dla tabeli **Kontakt** i wybierz szablon procesu przepływu pracy **Aktualizowanie dostawców typu Osoba w tabeli dostawców**.
5. Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika. Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.
6. Umożliwia aktywowanie przepływów pracy utworzonych dla tabel **Kontakt** i **Dostawca** w celu rozpoczęcia używania tabeli **Kontakt** do przechowywania informacji o dostawcy dla typu **Osoba**.
