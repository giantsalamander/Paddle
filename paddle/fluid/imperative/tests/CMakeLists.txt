if(WIN32)
    cc_test(nccl_context_test SRCS nccl_context_test.cc DEPS device_context)
else()
    cc_test(nccl_context_test SRCS nccl_context_test.cc DEPS nccl_context)
endif(WIN32)


cc_test(test_gradient_accmulator SRCS test_gradient_accmulator.cc DEPS memcpy selected_rows selected_rows_functor gradient_accumulator)
cc_test(test_layer SRCS test_layer.cc DEPS layer proto_desc operator op_registry variable_helper mul_op memcpy)
cc_test(test_prepare_op SRCS test_prepare_op.cc DEPS prepared_operator op_info split_op layer concat_and_split activation_op place)
cc_test(test_tracer SRCS test_tracer.cc DEPS tracer layer proto_desc operator op_registry variable_helper mul_op reduce_sum_op elementwise_add_op memcpy)
