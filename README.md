# How to change the tab panel position of TabControlExt to center

In TabControlExt the tab panel position can be changed using style. In the below sample and code snippet the position of tab panel is changed by changing the HorizontalAlignment property value of TabPanelAdv to Center using style.

## MainWindow.xaml:

        <Window x:Class="TabControlAlignment.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:TabControlAlignment"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        WindowStartupLocation="CenterScreen"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Window.Resources>
        <Style x:Key="NewtabControlExtStyle" TargetType="syncfusion:TabControlExt">
            <Setter Property="BorderThickness" Value="1"/>
            <Setter Property="Background" Value="{DynamicResource {x:Static SystemColors.ControlBrushKey}}"/>
            <Style.Triggers>
                <MultiDataTrigger>
                    <Setter Property="Template">
                        <Setter.Value>
                            <ControlTemplate TargetType="{x:Type syncfusion:TabControlExt}">
                                <Grid x:Name="TabControlGrid" Background="{TemplateBinding Background}"
                                ClipToBounds="False" SnapsToDevicePixels="True" KeyboardNavigation.TabNavigation="Local">
                                    <Grid.ColumnDefinitions>
                                        <ColumnDefinition x:Name="ColumnDefinition0"/>
                                        <ColumnDefinition x:Name="ColumnDefinition1" Width="0"/>
                                    </Grid.ColumnDefinitions>
                                    <Grid.RowDefinitions>
                                        <RowDefinition x:Name="RowDefinition0" Height="Auto"/>
                                        <RowDefinition x:Name="RowDefinition1" Height="*"/>
                                    </Grid.RowDefinitions>
                                    <syncfusion:HeaderPanel x:Name="HeaderPanel" Background="{TemplateBinding TabPanelBackground}"
                                    Grid.Column="0" Focusable="False" HorizontalAlignment="Stretch" Grid.Row="0" 
                                    VerticalAlignment="Stretch" Panel.ZIndex="1">
                                        <syncfusion:TabPanelAdv x:Name="PART_TabPanel" DockPanel.Dock="Right" Focusable="False"
                                        HorizontalAlignment="Center" Style="{TemplateBinding TabPanelStyle}" 
                                        VerticalAlignment="Stretch">
                                            <syncfusion:TabScrollViewer x:Name="PART_ScrollViewer" Focusable="False" 
                                            HorizontalScrollBarVisibility="Hidden" Margin="{Binding Margin,
                                            RelativeSource={RelativeSource FindAncestor, AncestorLevel=1,
                                            AncestorType={x:Type ContentPresenter}}}" PanningMode="HorizontalFirst" 
                                            VerticalScrollBarVisibility="Hidden">
                                                <syncfusion:TabLayoutPanel x:Name="PART_TabLayoutPanel" AllowDrop="True"
                                                ClipToBounds="True" HorizontalAlignment="Left" IsItemsHost="True" Margin="0,2,2,-1" 
                                                KeyboardNavigation.TabIndex="1" VerticalAlignment="Top"/>
                                            </syncfusion:TabScrollViewer>
                                        </syncfusion:TabPanelAdv>
                                    </syncfusion:HeaderPanel>
                                    <syncfusion:Border3D x:Name="ContentPanel" AllowDrop="True" 
                                    BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" 
                                    Grid.Column="0" CornerRadius="2" 
                                    KeyboardNavigation.DirectionalNavigation="Contained" Margin="0,1,0,0" 
                                    Grid.Row="1" KeyboardNavigation.TabIndex="2"
                                    KeyboardNavigation.TabNavigation="Local">
                                        <Border x:Name="PART_ContentPanelBorder" BorderBrush="#FF69A1BF" BorderThickness="0" 
                                        CornerRadius="2">
                                            <Border x:Name="PART_ContentPanelInnerBorder" 
                                            BorderBrush="{TemplateBinding BorderBrush}"
                                            BorderThickness="{TemplateBinding BorderThickness}" 
                                            Background="{TemplateBinding Background}" CornerRadius="2" Margin="3">
                                                <ContentPresenter x:Name="PART_SelectedContentHost" AllowDrop="True"
                                                ContentTemplate="{TemplateBinding SelectedContentTemplate}" 
                                                Content="{TemplateBinding SelectedContent}"
                                                ContentSource="SelectedContent" Margin="{TemplateBinding Padding}" 
                                                SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}"/>
                                            </Border>
                                        </Border>
                                    </syncfusion:Border3D>
                                </Grid>
                            </ControlTemplate>
                        </Setter.Value>
                    </Setter>
                </MultiDataTrigger>
            </Style.Triggers>
        </Style>
    </Window.Resources>

    <Grid>
        <syncfusion:TabControlExt Grid.Column="0" x:Name="MyTabCtrl"
                                  syncfusion:SkinStorage.VisualStyle="Metro"
                                  AllowDragDrop="False" 
                                  EnableLabelEdit="False"
                                  TabScrollStyle="Normal"
                                  ShowTabItemContextMenu="False" 
                                  CloseButtonType="Hide" 
                                  TabStripPlacement="Top"
                                  HorizontalAlignment="Center"
                                  ShowTabListContextMenu="False" 
                                  TabItemSelectedBackground="Red"
                                  TabItemHoverBackground ="ForestGreen"
                                  TabItemHoverForeground ="Black"
                                  TabItemHoverBorderBrush="DarkGreen"
                                  TabItemSelectedBorderBrush="Black"
                                  TabItemSelectedForeground="Yellow"
                                  BorderThickness="0" Width="750" Style="{DynamicResource NewtabControlExtStyle}">
            <syncfusion:TabControlExt.Resources>
                <Style TargetType="{x:Type syncfusion:HeaderPanel}">
                    <Setter Property="HorizontalAlignment" Value="Center" />
                </Style>
            </syncfusion:TabControlExt.Resources>

            <syncfusion:TabItemExt Header="Properties" Margin="0" HorizontalAlignment="Center">
                <TextBlock Text="Properties tab Description" />
            </syncfusion:TabItemExt>
            <syncfusion:TabItemExt Header="Solution" Margin="0" HorizontalAlignment="Center">
                <TextBlock Text="Solution tab Description" />
            </syncfusion:TabItemExt>
            <syncfusion:TabItemExt Header="Output" Margin="0" HorizontalAlignment="Center">
                <TextBlock Text="Output tab Description" />
            </syncfusion:TabItemExt>

        </syncfusion:TabControlExt>
    </Grid>
    </Window>

KB article - [How to change the tab panel position of TabControlExt to center](https://www.syncfusion.com/kb/11238/how-to-change-the-tab-panel-tabitem-headers-position-to-center-in-wpf-tabcontrol)
