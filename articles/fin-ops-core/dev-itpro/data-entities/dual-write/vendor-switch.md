---
title: Przełączanie się między projektami dostawcy
description: W tym temacie opisano sposób przełączania integracji danych dostawcy między aplikacjami Finance and Operations i Common Data Service.
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
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997559"
---
# <a name="switch-between-vendor-designs"></a>Przełączanie się między projektami dostawcy

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a>Przepływ danych dostawcy 

W przypadku wybrania opcji używania jednostki **Konto** do przechowywania dostawców typu **Organizacja** i jednostki **Kontakt** do przechowywania dostawców typu **Osoba** , należy skonfigurować następujące przepływy pracy. W przeciwnym razie ta konfiguracja nie jest wymagana.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Użycie rozszerzonego projektu dostawcy dla dostawców typu Organizacji

Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy. Zostanie utworzony przepływ pracy dla każdego szablonu.

+ Utwórz dostawców w jednostce kont
+ Utwórz Dostawców w Jednostce dostawców
+ Aktualizuj dostawców w jednostce kont
+ Aktualizuj Dostawców w Jednostce dostawców

Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:

1. Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Utwórz dostawców w jednostce kont**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla jednostki **konta**.

    ![Proces przepływu pracy Utwórz dostawców w jednostce kont](media/create_process.png)

2. Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców w jednostce kont**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla jednostki **konta**.
3. Utwórz nowy proces przepływu pracy dla jednostki **Konto** i wybierz szablonu procesu przepływu pracy jednostki **Utwórz dostawców w jednostce Dostawców**.
4. Utwórz nowy proces przepływu pracy dla jednostki **Konto** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców w jednostce Dostawców**.
5. Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika. Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.

    ![Przycisk Konwertuj na przepływ pracy w tle](media/background_workflow.png)

6. Umożliwia aktywowanie przepływów pracy utworzonych dla jednostek **Konto**  i **Dostawca** w celu rozpoczęcia używania jednostki **Konta** do przechowywania informacji o dostawcy dla typu **Organizacji**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Użycie rozszerzonego projektu dostawcy dla dostawców typu Osoby

Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy. Zostanie utworzony przepływ pracy dla każdego szablonu.

+ Tworzenie dostawców typu Osoba w jednostce dostawcy
+ Tworzenie dostawców typu Osoba w jednostce kontaktów
+ Aktualizacja dostawców typu Osoba w jednostce kontaktów
+ Aktualizacja dostawców typu Osoba w jednostce dostawcy

Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:

1. Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Tworzenie dostawców typu Osoba w jednostce kontaktów**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla jednostki **Kontakt**.
2. Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców typu Osoba w jednostce kontaktów**. Następnie wybierz opcję **OK**. Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla jednostki **Kontakt**.
3. Utwórz nowy proces przepływu pracy dla jednostki **Kontakt** i wybierz szablonu procesu przepływu pracy jednostki **Tworzenie dostawców typu Osoba w jednostce dostawcy**.
4. Utwórz nowy proces przepływu pracy dla jednostki **Kontakt** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców typu Osoba w jednostce dostawcy**.
5. Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika. Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.
6. Umożliwia aktywowanie przepływów pracy utworzonych dla jednostek **Kontakt**  i **Dostawca** w celu rozpoczęcia używania jednostki **Kontakt** do przechowywania informacji o dostawcy dla typu **Osoby**.
