---
title: Ustawianie zasobów systemu Azure dla fakturowania elektronicznego
description: Ten artykuł zawiera omówienie procesu konfigurowania zasobów Microsoft Azure dla fakturowania elektronicznego.
author: gionoder
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f11e4eac831d54a6cac765a5adc4e4ffddbe0a22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283094"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>Ustawianie zasobów systemu Azure dla fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

Proces konfigurowania zasobów Microsoft Azure dla fakturowania elektronicznego ma trzy kroki. Pierwsze dwa kroki, „Utwórz klucz systemu Azure w portalu Azure” i „Tworzenie konta magazynu Azure w portalu Azure” są obowiązkowe. Trzeci krok, „Konfigurowanie połączenia SharePoint”, jest opcjonalny.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Tworzenie klucza Azure Key Vault w portalu Azure Portal

Utwórz magazyn kluczy w ramach subskrypcji platformy Azure. Zaleca się utworzenie osobnego klucza dla fakturowania elektronicznego i nie łączenie ich z innymi aplikacjami. Utwórz jak najwięcej dokumentów w dokumentach elektronicznych. Musisz utworzyć co najmniej jeden klucz tajny, aby przechowywać token sygnatury dostępu współdzielonego (SAS) konta magazynu systemu Azure, które zostanie utworzenie w następnym kroku.

Aby uzyskać informacje dotyczące sposobu wykonania tego kroku, zobacz temat [Tworzenie klucza systemu Azure w portalu Azure](e-invoicing-create-azure-key-vault-azure-portal.md).

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Tworzenie konta magazynu usługi Azure w portalu Azure Portal

Użytkownik jest właścicielem wszystkich dokumentów i plików elektronicznych wygenerowanych przez usługę fakturowania elektronicznego lub wprowadza te dokumenty. Te dokumenty i pliki są przechowywane na koncie magazynu systemu Azure, które tworzysz w subskrypcji systemu Azure. Usługa będzie uzyskać dostęp do Konta magazynu przy użyciu tokenu SAS, który jest skojowany z klucza klucz-klucz tajny.

Aby uzyskać informacje dotyczące sposobu wykonania tego kroku, zobacz temat [Utwórz konto magazynu platformy Azure w portalu Azure](e-invoicing-create-azure-storage-account-azure-portal.md).

## <a name="configure-a-sharepoint-connection"></a>Konfigurowanie połączenia usługi SharePoint

W niektórych scenariuszach może być konieczne zapisanie plików elektronicznych SharePoint i pobranie ich z systemu SharePoint. Aby mieć pewność, że usługa fakturowania elektronicznego będzie mieć dostęp do folderów SharePoint, skonfiguruj dostęp do systemu SharePoint.

Aby uzyskać informacje dotyczące sposobu wykonania tego kroku, zobacz [Konfigurowanie połączenia SharePoint](e-invoicing-create-sharepoint-connection.md).
