# Tracelog
Some FTrace log

#how to run FTrace

debugfs=/sys/kernel/debug
echo nop > $debugfs/tracing/current_tracer
echo 0 > $debugfs/tracing/tracing_on
#echo $$ > $debugfs/tracing/set_ftrace_pid
echo function_graph > $debugfs/tracing/current_tracer
#replace test_proc_show by your function name
#echo finish_task_switch > $debugfs/tracing/set_graph_function
echo > $debugfs/tracing/set_graph_function 
echo funcgraph-abstime > $debugfs/tracing/trace_options
#local global counter uptime perf mono mono_raw boot x86-tsc
echo x86-tsc > $debugfs/tracing/trace_clock
#delta absolute
#echo absolute > $debugfs/tracing/timestamp_mode
#./"$@"
echo $(pidof test) > $debugfs/tracing/set_ftrace_pid
echo 1 > $debugfs/tracing/tracing_on
#sleep 15s
#echo "begin"
#./"$@"

#echo "close trace"
#echo 0 > $debugfs/tracing/tracing_on
#sleep 5s
#echo "begin cat"
#cat /sys/kernel/debug/tracing/trace > local.txt

#second method:trace-cmd
