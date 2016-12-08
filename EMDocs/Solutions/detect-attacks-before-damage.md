---
title: "在攻击造成损害前检测出攻击 | Azure Active Directory 信息保护"
description: "一个方案，描述如何使用企业移动性 + 安全性，通过利用高级威胁分析、Cloud App Security 和 Azure Active Directory Premium，保护公司数据，使其免受攻击。"
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 12/7/2016
ms.topic: solution
ms.prod: 
ms.service: ems
ms.technology: techgroup-identity
ms.assetid: de0a7e70-008b-45c1-bba8-f033b1f62194
ms.reviewer: v-craic
ms.suite: ems
ms.custom: active-directory, advanced-threat-analytics, cloud-app-security
translationtype: Human Translation
ms.sourcegitcommit: 0fd6f5b47ecd3aacbd0fd0c9cf76b90dcd68eaf4
ms.openlocfilehash: 449df764d3979f8030f8d35d8f6920dedb64b239


---

# <a name="detect-attacks-before-they-cause-damage"></a>在攻击造成损害前检测出攻击
要建立强大的安全保障，就需要设立高级的检测系统，这种检测系统应能够在威胁造成重大损害之前识别威胁。 组织能够无缝利用 Microsoft 安全智能来检测本地和云中的可疑活动。

强大的检测系统必须能够通过深层次可见性和持续的行为分析来发现可疑活动和确定威胁。 这让 IT 人员能够迅速针对检测到的攻击采取相应措施，并通过强大的支持实现高效恢复。


## <a name="how-can-enterprise-mobility-security-help-you"></a>企业移动性 + 安全性可提供哪些帮助？
Microsoft 企业移动性 + 安全性让 IT 人员能够使用革新性的行为分析和异常检测技术，确定组织中本地和云中的攻击者。  这将帮助 IT 人员检测出系统中的已知恶意攻击和已知安全漏洞。

## <a name="recommended-solution"></a>建议的解决方案
为满足此方案的要求，EMS 使用[高级威胁分析](https://docs.microsoft.com/en-us/advanced-threat-analytics/)、[Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security) 和 [Azure Active Directory Premium](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-get-started-premium)。 通过实施这些技术，组织将能够：

- 使用革新性的行为分析和异常检测技术（利用机器学习）检测或识别异常行为
- 检测已知恶意攻击（即传递哈希、传递票证）和已知安全漏洞
- 专注于重要方面和相关攻击信息
- 识别显示出安全漏洞可能性的异常和违反策略的行为

下图总结了此方案涉及的功能以及如何使用这些功能保护资源：

![图示：各个产品解决方案的功能及其提供攻击保护的工作原理。](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig1.png)

# <a name="how-to-detect-attacks-before-they-cause-damage"></a>如何在攻击造成损害前检测出攻击
一直以来，安全方面的投资仅侧重于保护。 但现如今，良好的检测和应对也成为必备条件。 IT 组织应侧重于一种方法，这种方法专注于如何提供威胁防护及检测和应对威胁。

![图示：持续提供威胁防护及检测、响应威胁的过程。](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig2.png)

IT 人员必须要考虑如何正确保护本地或云中的标识、数据、应用程序、设备和基础结构。  这需要一种实现安全的方法，这种方法应将从传感器到数据中心的所有端点纳入考虑。 过去，IT 管理员依靠恶意软件签名来识别威胁。

当用户凭据被盗时，传统的 IT 安全工具针对复杂的网络安全攻击只能提供有限的保护。 初始设置、创建规则和微调的实施缓慢而复杂，且可能需要花费数年的时间。 每天都会收到多个满是误报的报告。 大多数情况下，没有用来查看这些信息的资源，即使能够查看，可能仍无法得到答案，因为这些工具的主要功能是保护外围网络，阻止攻击者获得访问权限。 而如今，需要一种不同的方法来应对复杂的网络安全攻击。

在此全新的网络安全攻击背景下，要想减少威胁，IT 人员需要革新性的威胁检测解决方案，利用行为分析和机器学习技术，快速识别全新的威胁。  通过利用 ATA 和 Cloud App Security 来检测本地和云中的攻击，IT 人员能够在事件对环境造成重大损害之前快速应对事件。

在本地实施 ATA 之前，请阅读 [ATA 容量规划](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-capacity-planning)，另请阅读 [ATA 先决条件](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-prerequisites)，了解安装 ATA 之前的一般注意事项。 使用[预安装清单](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/preinstall-ata)验证基础结构是否已准备好接收 ATA。 完成此规划和验证阶段后，便随时可[部署 ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/install-ata-step1)。 将 ATA 部署到环境后，只需采用最小配置，它会立即开始了解环境，并在找到已知恶意攻击时触发警报。 按照步骤 1，使用 [ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/understand-explore/what-is-ata) 识别本地可疑活动。

为检测云应用威胁，此方案使用 [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security)。 确保按照[常规设置说明](https://docs.microsoft.com/en-us/cloud-app-security/general-setup)设置 Cloud App Security，并使用[云发现](https://docs.microsoft.com/en-us/cloud-app-security/set-up-cloud-discovery)选项，对照 Cloud App Security 的云应用目录分析流量日志。 按照步骤 2，使用 Cloud App Security 检测威胁和违规行为及情况。

## <a name="how-to-implement-this-solution"></a>实现本解决方案的方式
按下列步骤，实施[高级威胁分析](https://docs.microsoft.com/en-us/advanced-threat-analytics/)和 [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security)：

- 步骤 1：使用高级威胁分析 (ATA) 检测本地可疑活动
- 步骤 2：使用 Cloud App Security 针对云应用检测威胁和违规行为及情况  

### <a name="step-1-using-ata-to-detect-suspicious-activity"></a>步骤 1：使用 ATA 检测可疑活动
没完没了的传统安全工具报告和筛选报告以确定重要的相关警报会极大降低成效。 ATA 提供易于使用、可轻松向下钻取、类似于社交媒体源的报表，可帮助 IT 人员快速定位重要内容。 将这些数量巨大的数据以时间线的形式呈现，为你提供强大的客观判断力和洞见：谁访问了什么内容、访问的时间以及访问数据的方式。

在 ATA 中打开[攻击时间线](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/working-with-suspicious-activities)后，会看到一个含有可疑活动的综合报表，其中显示涉及活动的[实体](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-architecture)及相关建议：

![攻击时间线和可疑活动报表的屏幕截图。](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig3.png)

在此示例中，有一个事件，指示使用传递票证攻击实施身份盗用的可疑活动。 还会获得一个可用于初步补救步骤的建议列表。 在此示例中，当管理员的 Kerberos 票证从服务器 SHAREDADMIN-SRV 被窃取到服务器 EXTVENDOR-TS 中以用于访问 DC01 时，ATA 发出了警报。 可通过单击此事件中的任何对象，进行进一步调查。 例如，通过单击外部供应商终端服务器 (EXTVENDOR-TS)，可访问涉及此服务器的所有[可疑活动](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/working-with-suspicious-activities)。

ATA 同时在其用于确定和用于检测的引擎中使用机器学习，以了解用户和实体的常规行为模式，正是这种独特的功能让我们能够跨各种不同的攻击媒介提供及时准确的警报。


### <a name="step-2-using-cloud-app-security-to-detect-threats-and-policy-violations-for-cloud-apps"></a>步骤 2：使用 Cloud App Security 针对云应用检测威胁和违规行为及情况

越来越多的组织开始采用 SaaS 应用，不仅是为了降低成本，也为了获得竞争优势，如加速投放市场和更好的协作。 即使公司不使用云应用程序，其员工却很可能在使用。 据研究，超过 80% 的雇员承认在工作中使用未经批准的 SaaS 应用。

根据这种快速向云应用过渡的情况，我们知道你可能正在考虑在云中存储公司数据并探索如何让各地用户对其进行访问而无需实现全面的可见性、审核或控制。 旧有的安全解决方案并不用于保护 SaaS 应用程序中的数据。 防火墙和 IPS 等传统网络安全解决方案不提供针对特定于各应用程序的事务以及非本地流量的可见性，包括数据使用和存储的方式。 经典控件无法为云应用提供保护，因为它们只监视一小部分云流量，且对应用级活动的理解有限。

那么如何维持云应用的可见性、控制和保护？ 我们为你提供了解决方案：

Microsoft Cloud App Security 是一种综合性服务，可提供针对云应用程序的更深层次的可见性、全面控制和更强的保护。 Cloud App Security 旨在帮助扩展可在本地实现的云应用程序可见性和对其的审核和控制。

Cloud App Security 不仅提供针对云应用程序的可见性和控制，同时提供强大的威胁防护，并通过大量的 Microsoft 威胁智能和研究增强成效。 你能够识别高风险使用事件和安全事件，并检测异常用户行为，以防止威胁。

访问 Cloud App Security 仪表板时，会获取一个有关云应用安全状态的综合视图，其中包含一个专用于警报的部分：

![一个屏幕截图，显示含有打开的警报的 Cloud App Security 仪表盘。](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig6.png)

可单击“警报”菜单以访问[警报中心](https://docs.microsoft.com/en-us/cloud-app-security/monitor-alerts)。 通知中心收集各种类别的警报，包括威胁检测、特权帐户和违规行为。

![警报中心的屏幕截图，其中显示了所有警报的列表。](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig5.png)

通知中心收集由 Cloud App Security 标识的所有红色标志，包括异常和威胁检测违规行为及特权帐户。 Cloud App Security 高级机器学习启发会通过行为分析了解和学习每个用户与每个云应用的交互方式，评估每项事务中的风险。

当调查警报时，可单击警报名称，以获取有关警报的详细信息。 下面示例中的警报引用[文件策略](https://docs.microsoft.com/en-us/cloud-app-security/data-protection-policies) *公用共享机密文件*中的一个匹配项，该项被视为具有高优先级，因为它可能会导致数据泄露。   

![其中一个警报的特定详细信息的屏幕截图。](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig7.png)

上一个示例基于违反策略的情况，而 Cloud App Security 还可以[检测异常](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy#anomaly-detection-policy-reference)。 Cloud App Security 试运行期为 7 天，在此期间不会将任何新用户、活动、设备标记为异常。 之后，系统会将每个会话与活动 - 过去一个月检测到的用户处于活动状态时的时间、IP 地址、设备等信息 - 进行比较，并会向这些活动提供一个风险评分。 对这种类型的警报的描述称为常规异常检测，单击它便会看到一个类似于以下的屏幕：

![一个屏幕截图，显示 Cloud App Security 所检测到的异常。](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig8.png)

在此页上，可以看到触发该警报的用户、IP 地址、用户的组成员身份和有关此可疑行为的详细信息。 可以查看关于此活动的更多详细信息，其中包括失败的登录尝试次数、登录始发位置以及用于执行登录尝试的应用。



<!--HONumber=Dec16_HO1-->


